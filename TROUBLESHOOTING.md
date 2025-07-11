# Troubleshooting - SCRCPY WiFi Manager

## 🔍 Diagnóstico Automático

Primeiro, sempre use o diagnóstico automático do script:
```bash
./sms.sh
# Menu > Diagnóstico > Diagnóstico completo
```

## 📱 Problemas com Android

### ❌ Dispositivo não aparece no `adb devices`

**Causas possíveis:**
- Depuração USB desabilitada
- Cabo USB defeituoso
- Drivers não instalados
- Autorização negada

**Soluções:**
```bash
# 1. Verificar configurações do Android
Configurações > Opções do desenvolvedor > Depuração USB: ✅ Ativado

# 2. Testar cabo USB
- Tente outro cabo USB
- Teste outra porta USB no Mac
- Certifique-se que o cabo suporta dados (não apenas carregamento)

# 3. Autorização
- Aceite o popup "Permitir depuração USB"
- Marque "Sempre permitir deste computador"

# 4. Reiniciar servidor ADB
adb kill-server && adb start-server
```

### ❌ Dispositivo aparece como "unauthorized"

**Solução:**
```bash
# 1. Revogar autorizações
adb kill-server
# No Android: Configurações > Opções do desenvolvedor > Revogar autorizações de depuração USB

# 2. Reconectar
adb start-server
# Aceite novamente a autorização no celular
```

## 🌐 Problemas de Rede WiFi

### ❌ Não consegue obter IP do dispositivo

**Verificações:**
```bash
# 1. WiFi ativo no celular
adb -s DEVICE_ID shell dumpsys wifi | grep "Wi-Fi is"

# 2. Obter IP manualmente
adb -s DEVICE_ID shell ip route | grep wlan0
adb -s DEVICE_ID shell ifconfig wlan0
```

**Soluções:**
- Desconecte e reconecte o WiFi no celular
- Tente usar hotspot do celular
- Verifique se não há proxy configurado

### ❌ Mac e Android em redes diferentes

**Verificar redes:**
```bash
# IP do Mac
ifconfig | grep "inet " | grep -v 127.0.0.1

# IP do Android
adb -s DEVICE_ID shell ip route | grep wlan0
```

**Soluções:**
- Conecte ambos na mesma rede WiFi
- Use hotspot do celular
- Verifique configurações de rede corporativa

### ❌ Ping falha entre dispositivos

**Teste de conectividade:**
```bash
# Testar ping
ping -c 3 IP_DO_ANDROID

# Verificar firewall
sudo pfctl -s rules | grep 5555
```

**Soluções:**
- Desabilite temporariamente o firewall do Mac
- Configure roteador para permitir comunicação entre dispositivos
- Tente rede doméstica ao invés de corporativa
- Verifique se existe alguma VPN ativada

## 🔧 Problemas com scrcpy

### ❌ scrcpy não encontrado

**Instalação:**
```bash
# Via Homebrew
brew install scrcpy

# Verificar instalação
scrcpy --version
which scrcpy
```

### ❌ scrcpy falha ao conectar

**Diagnóstico:**
```bash
# Teste com debug
scrcpy -s DEVICE_ID --verbosity=debug

# Teste via USB primeiro
scrcpy -s DEVICE_ID

# Teste via WiFi
scrcpy -s IP_ADDRESS:5555
```

**Soluções:**
- Atualize o scrcpy: `brew upgrade scrcpy`
- Verifique compatibilidade de versão
- Tente com opções mínimas: `scrcpy -s DEVICE_ID --no-audio`

## 🔌 Problemas de Conexão TCP/IP

### ❌ `adb connect` falha

**Verificações:**
```bash
# 1. Verificar se porta TCP está configurada
adb -s DEVICE_ID tcpip 5555

# 2. Aguardar alguns segundos
sleep 5

# 3. Tentar conectar
adb connect IP_ADDRESS:5555

# 4. Verificar conexão
adb devices
```

**Soluções:**
- Aguarde mais tempo após `tcpip 5555`
- Tente múltiplas vezes
- Reinicie o WiFi no celular
- Use `adb disconnect` antes de tentar novamente

### ❌ Conexão instável

**Diagnóstico:**
```bash
# Verificar processos ADB
ps aux | grep adb

# Verificar porta em uso
lsof -i :5555

# Testar estabilidade da rede
ping -c 10 IP_DO_ANDROID
```

**Soluções:**
- Melhore a qualidade do sinal WiFi
- Aproxime dispositivos do roteador
- Reduza qualidade do vídeo no scrcpy
- Use cabo USB para conexão mais estável

## 🏢 Problemas em Redes Corporativas

### ❌ Isolamento de dispositivos

**Características:**
- Ping falha mesmo estando na mesma rede
- Conexão TCP/IP é bloqueada
- Firewall corporativo muito restritivo

**Soluções:**
```bash
# 1. Usar hotspot do celular
# No Android: Configurações > Hotspot > Ativar
# No Mac: Conectar na rede do celular

# 2. Solicitar liberação da porta 5555
# Contatar TI para liberar porta 5555 TCP

# 3. Usar VPN
# Configurar VPN que permita comunicação local
```

## 🐛 Problemas de Versão

### ❌ Incompatibilidade scrcpy 3.x vs 2.x

**Sintomas:**
- Opções não reconhecidas
- Erro de sintaxe de comando
- Funcionalidades não disponíveis

**Verificar versão:**
```bash
scrcpy --version
scrcpy --help | head -20
```

**Soluções:**
- Atualize para scrcpy 3.x: `brew upgrade scrcpy`
- Ajuste opções para versão correta
- Use o script que detecta versão automaticamente

## 🔄 Problemas de Performance

### ❌ Lag/Latência alta

**Otimizações:**
```bash
# Reduzir qualidade
scrcpy -s DEVICE --max-fps=30 --video-bit-rate=2M --max-size=1080

# Desabilitar áudio
scrcpy -s DEVICE --no-audio

# Usar codec eficiente
scrcpy -s DEVICE --video-codec=h264
```

### ❌ Vídeo travando

**Soluções:**
```bash
# Reduzir resolução
scrcpy -s DEVICE --max-size=720

# Limitar FPS
scrcpy -s DEVICE --max-fps=30

# Usar conexão USB
scrcpy -s DEVICE_ID  # Via USB
```

## 📊 Logs e Debug

### 🔍 Ativar logs detalhados

**No script:**
```bash
# Editar sms.sh
DEBUG=true
```

**No scrcpy:**
```bash
scrcpy -s DEVICE --verbosity=debug
```

### 📁 Localização dos logs

```bash
# Logs do script
/tmp/scrcpy_test.log
/tmp/scrcpy_quick_test.log

# Logs do sistema macOS
log show --predicate 'process == "adb"' --info --last 10m
```

## 🛠️ Comandos de Emergência

### 🔄 Reset completo

```bash
# 1. Matar todos os processos
killall adb
killall scrcpy

# 2. Reiniciar servidor ADB
adb kill-server
adb start-server

# 3. Desconectar todos os dispositivos WiFi
adb disconnect

# 4. Listar dispositivos
adb devices -l

# 5. Testar conexão básica
adb -s DEVICE_ID shell echo "test"
```

### 🔄 Reinstalar dependências

```bash
# Remover e reinstalar scrcpy
brew uninstall scrcpy
brew install scrcpy

# Remover e reinstalar adb
brew uninstall --cask android-platform-tools
brew install --cask android-platform-tools

# Verificar instalação
scrcpy --version
adb version
```

## 📞 Quando Pedir Ajuda

### 📋 Informações úteis para suporte

```bash
# Sistema
uname -a
sw_vers

# Versões
scrcpy --version
adb version
brew --version

# Dispositivos
adb devices -l

# Rede
ifconfig | grep "inet "
ping -c 3 IP_DO_ANDROID

# Logs
cat /tmp/scrcpy_test.log
```

### 🔍 Comandos de diagnóstico

```bash
# Execute antes de pedir ajuda
./sms.sh
# Menu > Diagnóstico > Diagnóstico completo

# Capturar saída
./sms.sh > diagnostico.txt 2>&1
```

## 🌟 Dicas Avançadas

### ⚡ Otimizar conexão

```bash
# Configurações recomendadas para gaming
scrcpy -s DEVICE --max-fps=60 --video-bit-rate=4M --max-size=1080 --audio-codec=opus

# Configurações para economia de bateria
scrcpy -s DEVICE --max-fps=30 --video-bit-rate=1M --max-size=720 --no-audio

# Configurações para apresentação
scrcpy -s DEVICE --max-fps=30 --video-bit-rate=2M --always-on-top --window-title="Android"
```

### 🔧 Automatizar conexão

```bash
# Criar alias no ~/.zshrc
alias android-connect="cd ~ && ./sms.sh"

# Script de conexão rápida
#!/bin/bash
adb kill-server
adb start-server
sleep 2
DEVICE=$(adb devices | sed 1d | awk '$2=="device" {print $1}' | grep -v '5555' | head -1)
if [ ! -z "$DEVICE" ]; then
    adb -s $DEVICE tcpip 5555
    sleep 5
    IP=$(adb -s $DEVICE shell ip route | awk '/wlan0/ {print $9}' | head -1)
    adb connect $IP:5555
    scrcpy -s $IP:5555
fi
```

---

**Para mais ajuda, use o diagnóstico automático do script ou consulte o README.md!** 🚀
