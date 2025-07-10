# SCRCPY WiFi Manager for macOS

![GitHub Gist](https://img.shields.io/badge/GitHub-Gist-blue?style=flat-square&logo=github)
![macOS](https://img.shields.io/badge/macOS-Compatible-blue?style=flat-square&logo=apple)
![scrcpy](https://img.shields.io/badge/scrcpy-3.2%2B-green?style=flat-square)
![Shell](https://img.shields.io/badge/Shell-Bash-4EAA25?style=flat-square&logo=gnu-bash)

Um gerenciador completo e intuitivo para conectar dispositivos Android ao macOS via WiFi usando scrcpy, com interface de menu interativa, diagnóstico avançado, configurações persistentes e troubleshooting automático.

## 🎯 Funcionalidades

### 🔗 Conexão
- **Múltiplos modos de conexão**: WiFi (padrão, baixa, alta e personalizada) e USB
- **Detecção automática de dispositivos** com suporte a múltiplos dispositivos
- **Configuração automática TCP/IP** com reconexão inteligente
- **Soluções rápidas** para problemas comuns de WiFi

### 🔧 Diagnóstico e Troubleshooting
- **Diagnóstico completo do sistema** com verificação de dependências
- **Troubleshooting avançado** com testes de conectividade
- **Logs detalhados** com sistema de debug configurável
- **Teste de ping** e verificação de rede automática

### 📱 Gerenciamento de Dispositivos
- **Listagem completa** de dispositivos USB e WiFi
- **Desconexão seletiva** de dispositivos WiFi
- **Reconexão automática** com configuração TCP/IP
- **Reset completo** de conexões ADB

### ⚙️ Configurações Avançadas
- **Configurações persistentes do scrcpy** (25+ opções)
- **Categorização organizada**: Controles, Vídeo, Áudio, Janela, Avançado
- **Instalação automática** de dependências (scrcpy, adb, Homebrew)
- **Compatibilidade** com scrcpy 2.x e 3.x

## 🚀 Instalação Rápida

```bash
# 1. Baixar o script
curl -o ~/sms.sh "https://gist.githubusercontent.com/USERNAME/GIST_ID/raw/sms.sh"

# 2. Dar permissão de execução
chmod +x ~/sms.sh

# 3. Executar
./sms.sh
```

## 📋 Pré-requisitos

- **macOS** (qualquer versão moderna)
- **Homebrew** (instalação automática disponível)
- **Android** com depuração USB habilitada
- **Mesmo WiFi** para Mac e Android

### Dependências Automaticamente Instaladas
- `scrcpy` (versão 2.x ou 3.x)
- `adb` (Android Debug Bridge)
- `brew` (se não estiver instalado)

## 🎛️ Menu Principal

```
╔══════════════════════════════════════════════════════════════╗
║                    SCRCPY WiFi Manager                    ║
║              Conecte seu Android via WiFi no Mac             ║
╚══════════════════════════════════════════════════════════════╝

Selecione uma categoria:

1. 🔗 Conectar Dispositivo
2. 🔧 Diagnóstico e Troubleshooting
3. 📱 Gerenciar Dispositivos
4. ⚙️  Configurações
0. 🚪 Sair
```

## 🔗 Opções de Conexão

### Perfis de Qualidade Pré-definidos
- **Padrão**: 2M bitrate, 60fps - Balanceado
- **Baixa**: 1M bitrate, 30fps - Redes lentas
- **Alta**: 8M bitrate, 60fps - Redes rápidas
- **Personalizada**: Configuração manual completa

### Modos de Conexão
- **WiFi**: Conexão sem fio (recomendado)
- **USB**: Conexão direta via cabo
- **Soluções rápidas**: Correção automática de problemas

## 🔧 Diagnóstico Avançado

### Verificações Automáticas
- ✅ Versões do scrcpy e adb
- ✅ Dispositivos conectados
- ✅ Processos em execução
- ✅ Portas em uso (5555)
- ✅ Conectividade de rede
- ✅ Teste de ping
- ✅ Compatibilidade de rede

### Logs Detalhados
- **Logs de sistema** com filtragem por processo
- **Logs de erro** com análise automática
- **Logs de debug** configuráveis
- **Logs de teste** para troubleshooting

## ⚙️ Configurações Persistentes do scrcpy

### Categorias de Configuração

#### 🎮 Controles
- `show-touches`: Mostrar toques na tela
- `no-control`: Desabilitar controle (apenas visualização)
- `stay-awake`: Manter dispositivo acordado

#### 🎥 Vídeo
- `max-size`: Resolução máxima
- `max-fps`: Taxa de quadros máxima
- `video-bit-rate`: Bitrate do vídeo
- `video-codec`: Codec de vídeo (h264, h265, av1)
- `crop`: Cortar área da tela
- `display-orientation`: Orientação da tela

#### 🔊 Áudio
- `audio-bit-rate`: Bitrate do áudio
- `audio-codec`: Codec de áudio (opus, aac, flac, raw)
- `audio-source`: Fonte de áudio
- `no-audio`: Desabilitar áudio

#### 🪟 Janela
- `window-title`: Título da janela
- `window-borderless`: Janela sem bordas
- `always-on-top`: Janela sempre no topo
- `fullscreen`: Modo tela cheia

#### 🔧 Avançado
- `turn-screen-off`: Desligar tela do dispositivo
- `power-off-on-close`: Desligar ao fechar
- `print-fps`: Mostrar FPS
- `no-clipboard-autosync`: Desabilitar sincronização
- `disable-screensaver`: Desabilitar proteção de tela
- `verbosity`: Nível de log (verbose, debug, info, warn, error)

## 🛠️ Troubleshooting Automático

### Problemas Comuns e Soluções

#### 📶 WiFi não conecta
```bash
# Soluções automáticas aplicadas:
1. Reiniciar servidor ADB
2. Reconfigurar modo TCP múltiplas vezes
3. Obter IP com métodos alternativos
4. Tentar conexão com retry inteligente
```

#### 🔌 USB não detecta
```bash
# Verificações automáticas:
1. Cabo USB funcionando
2. Depuração USB habilitada
3. Autorização aceita no celular
4. Drivers ADB instalados
```

#### 🌐 Rede incompatível
```bash
# Testes de rede:
1. Verificar se estão na mesma rede
2. Testar conectividade com ping
3. Verificar firewall/roteador
4. Detectar isolamento de dispositivos
```

## 📊 Instalação de Dependências

O script pode instalar automaticamente:

```bash
# Homebrew (se não estiver instalado)
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# scrcpy
brew install scrcpy

# Android Platform Tools (adb)
brew install --cask android-platform-tools
```

## 🔍 Comandos Úteis

### Verificação Manual
```bash
# Verificar dispositivos
adb devices -l

# Reiniciar ADB
adb kill-server && adb start-server

# Testar scrcpy via USB
scrcpy -s DEVICE_ID --verbosity=debug

# Conectar via WiFi manualmente
adb -s DEVICE_ID tcpip 5555
adb connect IP_ADDRESS:5555
```

### Diagnóstico de Rede
```bash
# Verificar IP do Mac
ifconfig | grep "inet " | grep -v 127.0.0.1

# Testar conectividade
ping -c 1 DEVICE_IP

# Verificar porta 5555
lsof -i :5555
```

## 🎯 Compatibilidade

### scrcpy Versions
- ✅ **scrcpy 3.2+** (totalmente compatível)
- ✅ **scrcpy 2.x** (compatível)
- ⚠️ **scrcpy 1.x** (funcionalidade limitada)

### Sistema Operacional
- ✅ **macOS Big Sur** (11.0+)
- ✅ **macOS Monterey** (12.0+)
- ✅ **macOS Ventura** (13.0+)
- ✅ **macOS Sonoma** (14.0+)
- ✅ **macOS Sequoia** (15.0+)

### Android
- ✅ **Android 5.0+** (API level 21+)
- ✅ **Todas as marcas** (Samsung, Xiaomi, OnePlus, etc.)
- ✅ **ROMs personalizadas** (LineageOS, etc.)

## 🐛 Logs e Debug

### Ativação de Debug
```bash
# Via menu: Configurações > Ativar/Desativar logs de debug
# Ou definir manualmente no script:
DEBUG=true
```

### Localização de Logs
```bash
# Logs de teste scrcpy
/tmp/scrcpy_test.log
/tmp/scrcpy_quick_test.log

# Logs do sistema (comando automático)
log show --predicate 'process == "adb"' --info --last 10m
```

## 🔐 Configurações de Segurança

### Configurações Recomendadas no Android
```
Configurações > Opções do desenvolvedor:
✅ Depuração USB
✅ Depuração USB (Modo de segurança)
✅ Permanecer ativo
✅ Depuração via WiFi (Android 11+)
```

### Firewall do macOS
```bash
# Verificar se a porta 5555 está bloqueada
sudo pfctl -s rules | grep 5555

# Permitir temporariamente (se necessário)
sudo pfctl -d  # Desabilitar firewall temporariamente
```

## 📈 Performance e Otimização

### Configurações Recomendadas por Cenário

#### 🎮 Gaming/Baixa Latência
```bash
max-fps: 60
video-bit-rate: 4M
max-size: 1080
audio-codec: opus
```

#### 💾 Economia de Dados
```bash
max-fps: 30
video-bit-rate: 1M
max-size: 720
no-audio: true
```

#### 🖥️ Apresentações
```bash
max-fps: 30
video-bit-rate: 2M
max-size: 1440
always-on-top: true
```

## 🔄 Atualizações

### Verificar Atualizações
```bash
# Verificar versão do scrcpy
scrcpy --version

# Atualizar via Homebrew
brew upgrade scrcpy

# Atualizar script (baixar novamente)
curl -o ~/sms.sh "https://gist.githubusercontent.com/USERNAME/GIST_ID/raw/sms.sh"
```

## 🆘 Suporte e Solução de Problemas

### Problemas Frequentes

#### ❌ "Nenhum dispositivo conectado"
- Verifique cabo USB
- Aceite autorização no celular
- Reinicie servidor ADB

#### ❌ "Não foi possível obter IP"
- Conecte ao WiFi no celular
- Verifique se WiFi está ativo
- Tente hotspot como teste

#### ❌ "Falha ao conectar via WiFi"
- Use soluções rápidas do menu
- Verifique firewall/roteador
- Tente rede diferente

#### ❌ "scrcpy não encontrado"
- Use menu de instalação automática
- Instale manualmente: `brew install scrcpy`

### Comandos de Diagnóstico
```bash
# Verificação completa
./sms.sh  # Menu: Diagnóstico > Diagnóstico completo

# Teste de conectividade
./sms.sh  # Menu: Diagnóstico > Testar conectividade WiFi

# Logs detalhados
./sms.sh  # Menu: Diagnóstico > Ver logs de erro
```

## 📞 Contato e Contribuição

### Autor
- **Nome**: Script desenvolvido para comunidade
- **Gist**: [Link do GitHub Gist](https://gist.github.com/USERNAME/GIST_ID)
- **Versão**: 3.2 (compatível com scrcpy 3.x)

### Contribuições
- 🐛 **Reportar bugs**: Use os issues do Gist
- 💡 **Sugestões**: Comentários são bem-vindos
- 🔧 **Melhorias**: Fork e pull requests aceitos

### Changelog
- **v3.2**: Compatibilidade com scrcpy 3.x, configurações persistentes
- **v3.1**: Menu interativo, diagnóstico avançado
- **v3.0**: Troubleshooting automático, instalação de dependências
- **v2.0**: Suporte a múltiplos dispositivos, soluções rápidas
- **v1.0**: Versão inicial com conexão básica WiFi

## 📄 Licença

Este script é fornecido "como está" sob licença MIT. Use por sua conta e risco.

---

### 🌟 Se este script te ajudou, considere deixar uma ⭐ no Gist!

**Última atualização**: Dezembro 2024
**Compatibilidade**: scrcpy 3.2+, macOS 11.0+, Android 5.0+

---

*Conecte seu Android ao Mac via WiFi de forma simples e eficiente!* 🚀📱💻
