# Instalação Rápida - SCRCPY WiFi Manager

## 🚀 Instalação em 3 Passos

### 1. Baixar o Script
```bash
curl -o ~/sms.sh "https://gist.githubusercontent.com/USERNAME/GIST_ID/raw/sms.sh"
```

### 2. Dar Permissão de Execução
```bash
chmod +x ~/sms.sh
```

### 3. Executar
```bash
./sms.sh
```

## 📋 Pré-requisitos

### No Android:
1. Ative as **Opções do Desenvolvedor**:
   - Vá em `Configurações > Sobre o telefone`
   - Toque 7 vezes em `Número da versão`

2. Ative a **Depuração USB**:
   - Vá em `Configurações > Opções do desenvolvedor`
   - Ative `Depuração USB`
   - Ative `Depuração USB (Modo de segurança)`

3. **Conecte ao WiFi** (mesma rede que o seu Mac)

### No Mac:
- **macOS 11.0+** (Big Sur ou superior)
- **Homebrew** (será instalado automaticamente se necessário)

## 🔧 Instalação Manual das Dependências

Se preferir instalar manualmente:

### Instalar Homebrew (se não tiver):
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Instalar scrcpy:
```bash
brew install scrcpy
```

### Instalar adb:
```bash
brew install --cask android-platform-tools
```

## 🎯 Primeiro Uso

1. **Conecte o celular via USB**
2. **Execute o script**: `./sms.sh`
3. **Aceite a autorização** no celular
4. **Escolha opção 1** (Conectar Dispositivo)
5. **Escolha opção 1** (WiFi Padrão)
6. **Aguarde a conexão** (pode levar até 30 segundos)

## 🆘 Problemas na Instalação?

### Dependências faltando:
- Use o menu: `Configurações > Verificar/Instalar dependências`

### Erro de permissão:
```bash
chmod +x sms.sh
```

### Cabo USB não detecta:
- Troque o cabo USB
- Tente outra porta USB
- Reinicie o celular

### WiFi não conecta:
- Use: `Conectar > Soluções rápidas`
- Tente uma rede doméstica
- Desative temporariamente o firewall

## 📞 Suporte

Se tiver problemas:
1. Use o **diagnóstico automático**: Menu > Diagnóstico > Diagnóstico completo
2. Consulte o **troubleshooting**: Menu > Diagnóstico > Troubleshooting avançado
3. Veja os **logs**: Menu > Diagnóstico > Ver logs de erro

## 🔄 Atualização

Para atualizar o script:
```bash
curl -o ~/sms.sh "https://gist.githubusercontent.com/USERNAME/GIST_ID/raw/sms.sh"
chmod +x ~/sms.sh
```

## ✅ Verificação da Instalação

Execute estes comandos para verificar:
```bash
# Verificar scrcpy
scrcpy --version

# Verificar adb
adb version

# Listar dispositivos
adb devices
```

---

**Pronto! Agora você pode usar o Android no Mac via WiFi!** 🎉📱💻
