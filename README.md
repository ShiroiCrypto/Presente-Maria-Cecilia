# 🎵 Momento Crush - Projeto Arduino

Projeto Arduino que toca **"Vampire Killer"** do Castlevania e executa transição suave de cores azul/roxo no LED RGB.

## 📋 Componentes Necessários

- **Arduino Uno** ou **Arduino Nano**
- **LED RGB** (Tipo **Ânodo Comum** - comum ligado ao +5V)
- **Buzzer Passivo**
- **Botão Pushbutton**
- Resistor 220Ω (opcional, para proteção do buzzer)

## 🔌 Conexões

### LED RGB (Ânodo Comum)
- **Pino R (Vermelho)** → Pino **9** do Arduino (PWM)
- **Pino G (Verde)** → Pino **10** do Arduino (PWM)
- **Pino B (Azul)** → Pino **11** do Arduino (PWM)
- **Ânodo Comum** → **+5V** do Arduino

### Buzzer Passivo
- **Terminal positivo** → Pino **7** do Arduino
- **Terminal negativo** → **GND** do Arduino

### Botão
- **Um terminal** → Pino **2** do Arduino
- **Outro terminal** → **GND** do Arduino

> **Nota:** O botão usa `INPUT_PULLUP`, então não é necessário resistor externo.

## 🎹 Funcionalidades

1. **Detecção de Botão com Debounce (50ms)**
   - Detecta borda de descida (pressionamento)
   - Evita múltiplas ativações por ruído

2. **Reprodução Musical**
   - Toca **"Vampire Killer"** do Castlevania
   - Melodia completa do tema clássico do jogo
   - Tempo ajustado para 130 BPM (tempo original)
   - Duração aproximada: ~30-40 segundos
   - Executa **uma vez** por pressionamento do botão

3. **Transição de Cores Azul/Roxo**
   - Durante e após a música, o LED executa transição suave entre tons de **azul e roxo**
   - Transição contínua e cíclica entre as cores
   - Intervalo de atualização: **30ms** (non-blocking)
   - Lógica invertida para LED de ânodo comum (255 = OFF, 0 = ON)
   - Cores mudam automaticamente criando um efeito visual hipnotizante

4. **Máquina de Estados Non-Blocking**
   - Sistema não trava durante execução
   - Permite resposta rápida a novos comandos

## 📝 Como Usar

1. Faça todas as conexões conforme o esquema acima
2. Abra o arquivo `MomentoCrush.ino` no Arduino IDE
3. Selecione a placa correta (Arduino Uno/Nano) e a porta serial
4. Faça o upload do código
5. Pressione o botão para ativar o sistema

## 🎵 Sequência de Execução

1. **Estado IDLE:** Sistema aguarda pressionamento do botão
2. **Estado PLAYING_MUSIC:** Toca "Vampire Killer" + transição de cores azul/roxo
3. **Estado COLOR_TRANSITION:** Continua transição de cores azul/roxo indefinidamente
4. **Pressionar botão novamente:** Reinicia música e cores do zero

## ⚙️ Configurações Ajustáveis

No código, você pode ajustar:

- `DEBOUNCE_DELAY`: Tempo de debounce do botão (padrão: 50ms)
- `COLOR_UPDATE_INTERVAL`: Intervalo entre atualizações das cores (padrão: 30ms)
- `colorSpeed`: Velocidade da transição de cores (padrão: 2 - aumente para mais rápido)
- `tempo`: BPM da música (padrão: 130 - aumente para mais rápido, diminua para mais lento)

## 📄 Licença

MIT License - Veja o arquivo LICENSE para mais detalhes.

---

**Desenvolvido com ❤️ para Maria Cecilia**
