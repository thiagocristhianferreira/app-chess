# app-chess

Jogo de xadrez para terminal escrito em **Java**, com tabuleiro colorido (códigos ANSI),
movimentação de peças, captura e troca de turnos. Projeto desenvolvido com foco em
Programação Orientada a Objetos (herança, abstração, encapsulamento e tratamento de exceções).

## Demonstração

```
8 R N B Q K B N R
7 P P P P P P P P
6 - - - - - - - -
5 - - - - - - - -
4 - - - - - - - -
3 - - - - - - - -
2 P P P P P P P P
1 R N B Q K B N R
  a b c d e f g h

Captured pieces:
White: []
Black: []

Turn : 1
Waiting player: WHITE

Source:
```

Legenda das peças: `K` Rei, `Q` Rainha, `R` Torre, `B` Bispo, `N` Cavalo, `P` Peão.
Peças brancas em branco, pretas em amarelo.

## Como executar

Pré-requisitos: **JDK 17** ou superior.

```bash
# compilar
javac -d out $(find src -name "*.java")

# executar
java -cp out application.Program
```

> No Windows (PowerShell), use o terminal do IntelliJ IDEA ou rode a classe
> `application.Program` diretamente pela IDE para que as cores ANSI sejam exibidas
> corretamente.

### Como jogar

1. Informe a posição de **origem** da peça (ex.: `e2`) e pressione Enter.
2. O tabuleiro destaca em azul os destinos possíveis da peça escolhida.
3. Informe a posição de **destino** (ex.: `e4`) e pressione Enter.

## Arquitetura

O código é dividido em três camadas:

| Pacote              | Responsabilidade                                                        |
| ------------------- | ----------------------------------------------------------------------- |
| `boardgame`         | Camada genérica de tabuleiro: `Board`, `Piece`, `Position`, exceções.   |
| `chess`             | Regras de xadrez: `ChessMatch`, `ChessPiece`, `ChessPosition`, `Color`. |
| `chess.pieces`      | Peças concretas: `King`, `Queen`, `Rook`, `Bishop`, `Knight`, `Pawn`.   |
| `application`       | Interface de terminal (`UI`) e ponto de entrada (`Program`).            |

## Status do projeto

> ✅ **Completo.** Todas as peças e regras principais do xadrez estão implementadas.

Implementado:

- [x] Tabuleiro 8x8 com posicionamento inicial padrão
- [x] Todas as peças: **Rei, Rainha, Torre, Bispo, Cavalo e Peão**
- [x] Cálculo e exibição dos movimentos possíveis
- [x] Captura de peças e listagem das peças capturadas
- [x] Alternância de turnos entre os jogadores (branco/preto)
- [x] **Xeque** e **xeque-mate** (com detecção de vencedor)
- [x] Impedimento de jogadas que deixam o próprio rei em xeque
- [x] Jogadas especiais: **roque**, **en passant** e **promoção**
- [x] Tratamento de exceções (`ChessException`, `BoardExeption`)

## Licença

Distribuído sob a licença [MIT](LICENSE).
