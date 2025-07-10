#!/bin/bash

# Exemplo de uso do SCRCPY WiFi Manager
# Este arquivo mostra como usar o script sms.sh de diferentes formas

echo "=== SCRCPY WiFi Manager - Exemplos de Uso ==="
echo

# 1. Execução básica com menu interativo
echo "1. Execução básica:"
echo "   ./sms.sh"
echo "   - Abre o menu interativo"
echo "   - Escolha opção 1 para conectar"
echo "   - Siga as instruções na tela"
echo

# 2. Verificar dependências
echo "2. Verificar dependências:"
echo "   - No menu principal, escolha '4' (Configurações)"
echo "   - Depois escolha '5' (Verificar/Instalar dependências)"
echo "   - O script instalará automaticamente se necessário"
echo

# 3. Usar diagnóstico para problemas
echo "3. Diagnosticar problemas:"
echo "   - No menu principal, escolha '2' (Diagnóstico)"
echo "   - Depois escolha '1' (Diagnóstico completo)"
echo "   - Veja relatório detalhado do sistema"
echo

# 4. Conectar com qualidades diferentes
echo "4. Diferentes qualidades de conexão:"
echo "   - Opção 1: Conectar > Padrão (2M, 60fps)"
echo "   - Opção 2: Conectar > Baixa (1M, 30fps)"
echo "   - Opção 3: Conectar > Alta (8M, 60fps)"
echo "   - Opção 4: Conectar > Personalizada"
echo

# 5. Configurar opções do scrcpy
echo "5. Configurar opções do scrcpy:"
echo "   - Vá em Configurações > Configurar opções do scrcpy"
echo "   - Escolha categoria: Controles, Vídeo, Áudio, Janela, Avançado"
echo "   - Configure as opções desejadas"
echo "   - As configurações são salvas permanentemente"
echo

# 6. Usar soluções rápidas
echo "6. Soluções rápidas para problemas WiFi:"
echo "   - Vá em Conectar > Soluções rápidas"
echo "   - O script tentará resolver problemas automaticamente"
echo "   - Inclui restart ADB, reconfiguração TCP, etc."
echo

# 7. Gerenciar dispositivos
echo "7. Gerenciar dispositivos:"
echo "   - Vá em Gerenciar Dispositivos"
echo "   - Liste, desconecte, reconecte ou reset dispositivos"
echo "   - Útil quando há múltiplos dispositivos conectados"
echo

# 8. Configurações avançadas
echo "8. Configurações avançadas:"
echo "   - Debug: Ativar/desativar logs detalhados"
echo "   - Timeout: Configurar tempo limite de conexão"
echo "   - Informações: Ver detalhes do sistema"
echo

# 9. Troubleshooting
echo "9. Troubleshooting avançado:"
echo "   - Diagnóstico > Troubleshooting avançado"
echo "   - Testa conexão USB, WiFi, ping, scrcpy"
echo "   - Fornece soluções específicas para problemas"
echo

# 10. Logs e debug
echo "10. Logs e debug:"
echo "    - Diagnóstico > Ver logs de erro detalhados"
echo "    - Logs ficam em /tmp/scrcpy_test.log"
echo "    - Configure DEBUG=true no script para mais detalhes"
echo

echo "=== COMANDOS MANUAIS ÚTEIS ==="
echo

echo "# Verificar dispositivos conectados:"
echo "adb devices -l"
echo

echo "# Conectar manualmente via WiFi:"
echo "adb -s DEVICE_ID tcpip 5555"
echo "adb connect IP_ADDRESS:5555"
echo "scrcpy -s IP_ADDRESS:5555"
echo

echo "# Testar scrcpy com debug:"
echo "scrcpy -s DEVICE_ID --verbosity=debug"
echo

echo "# Reinstalar dependências:"
echo "brew install scrcpy"
echo "brew install --cask android-platform-tools"
echo

echo "=== ESTRUTURA DO MENU ==="
echo

echo "Menu Principal:"
echo "├── 1. Conectar Dispositivo"
echo "│   ├── 1. WiFi (Padrão)"
echo "│   ├── 2. WiFi (Baixa qualidade)"
echo "│   ├── 3. WiFi (Alta qualidade)"
echo "│   ├── 4. WiFi (Personalizada)"
echo "│   ├── 5. USB"
echo "│   └── 6. Soluções rápidas"
echo "├── 2. Diagnóstico e Troubleshooting"
echo "│   ├── 1. Diagnóstico completo"
echo "│   ├── 2. Troubleshooting avançado"
echo "│   ├── 3. Testar conectividade WiFi"
echo "│   └── 4. Ver logs de erro"
echo "├── 3. Gerenciar Dispositivos"
echo "│   ├── 1. Listar dispositivos"
echo "│   ├── 2. Desconectar WiFi"
echo "│   ├── 3. Reconectar WiFi"
echo "│   └── 4. Reset conexões ADB"
echo "└── 4. Configurações"
echo "    ├── 1. Toggle debug"
echo "    ├── 2. Configurar scrcpy"
echo "    ├── 3. Ver configurações"
echo "    ├── 4. Configurar timeout"
echo "    ├── 5. Instalar dependências"
echo "    ├── 6. Reset configurações"
echo "    └── 7. Informações do sistema"
echo

echo "=== CONFIGURAÇÕES SCRCPY DISPONÍVEIS ==="
echo

echo "Controles:"
echo "- show-touches: Mostrar toques na tela"
echo "- stay-awake: Manter dispositivo acordado"
echo "- no-control: Apenas visualização"
echo "- turn-screen-off: Desligar tela do dispositivo"
echo

echo "Vídeo:"
echo "- max-size: Resolução máxima (ex: 1080)"
echo "- max-fps: FPS máximo (ex: 60)"
echo "- video-bit-rate: Bitrate do vídeo (ex: 2M)"
echo "- video-codec: Codec (h264, h265, av1)"
echo "- no-video: Desabilitar vídeo"
echo

echo "Áudio:"
echo "- audio-bit-rate: Bitrate do áudio (ex: 128k)"
echo "- audio-codec: Codec (opus, aac, flac, raw)"
echo "- audio-source: Fonte de áudio"
echo "- no-audio: Desabilitar áudio"
echo

echo "Janela:"
echo "- window-title: Título da janela"
echo "- always-on-top: Sempre no topo"
echo "- fullscreen: Tela cheia"
echo "- window-borderless: Sem bordas"
echo

echo "Avançado:"
echo "- power-off-on-close: Desligar ao fechar"
echo "- print-fps: Mostrar FPS"
echo "- no-clipboard-autosync: Sem sincronização"
echo "- disable-screensaver: Sem proteção de tela"
echo "- verbosity: Nível de log (verbose, debug, info, warn, error)"
echo

echo "=== PROBLEMAS COMUNS E SOLUÇÕES ==="
echo

echo "❌ 'Nenhum dispositivo conectado':"
echo "   → Verifique cabo USB"
echo "   → Aceite autorização no celular"
echo "   → Use: adb kill-server && adb start-server"
echo

echo "❌ 'Não foi possível obter IP':"
echo "   → Conecte ao WiFi no celular"
echo "   → Verifique se WiFi está ativo"
echo "   → Tente usar hotspot como teste"
echo

echo "❌ 'Falha ao conectar via WiFi':"
echo "   → Use soluções rápidas do menu"
echo "   → Verifique firewall/roteador"
echo "   → Tente rede doméstica"
echo

echo "❌ 'scrcpy não encontrado':"
echo "   → Use instalação automática do menu"
echo "   → Ou: brew install scrcpy"
echo

echo "=== PARA MAIS INFORMAÇÕES ==="
echo "Execute: ./sms.sh"
echo "Vá em: Configurações > Informações do sistema"
echo "Ou: Diagnóstico > Diagnóstico completo"
echo

echo "GitHub Gist: https://gist.github.com/USERNAME/GIST_ID"
echo "Compatível com: scrcpy 3.2+, macOS 11.0+, Android 5.0+"
