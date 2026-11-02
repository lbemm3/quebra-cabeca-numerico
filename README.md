[README (7).md](https://github.com/user-attachments/files/34280729/README.7.md)
# Jogo dos 15 e a paridade das permutações

Quebra-cabeça deslizante com explicação matemática: só duas peças estão fora do lugar, e ordenar o tabuleiro é mais difícil do que parece.

O tabuleiro começa com as peças 1 a 13 nas casas corretas e as peças 14 e 15 trocadas. O objetivo é ordená-lo deslizando as peças, e a análise mostra que isso é impossível.

## O que a página oferece

- **Simulador:** clique em uma peça vizinha ao espaço vazio para movê-la.
- **Controles:** *Desfazer* volta um movimento, *Reiniciar* restaura a configuração escolhida e *Embaralhar* faz 80 movimentos válidos aleatórios.
- **Início:** o seletor alterna entre Desafio (14 e 15 trocados) e Treino (tabuleiro ordenado).
- **Painel de estado:** vetor de estado, inversões e sinal da permutação.
- **Análise do invariante:** a opção *Mostrar análise do invariante* exibe a distância do vazio ao canto, o invariante e se a configuração tem solução. Ela fica desligada por padrão, para que os alunos tentem resolver o jogo antes de ver a resposta.
- **Histórico:** cada movimento aparece como uma transposição de posições `(p ⇄ q)`, com a composição acumulada `τₙ ∘ … ∘ τ₁`.
- **Explicação matemática:** posições como permutação, transposições, composição, invariante com demonstração e a contagem de `16!/2` configurações resolvíveis.

## A ideia matemática

O espaço vazio conta como a peça 16. Um estado é uma permutação `σ` das posições 1 a 16, e o jogo resolvido é a identidade.

Cada movimento é uma transposição de duas posições e, portanto, troca o sinal de `σ`. Seja `d` a distância do vazio ao canto inferior direito. Cada movimento também muda a paridade de `d`. Logo, o produto `sgn(σ) · (−1)^d` é invariante.

No início do jogo, `σ` tem 1 inversão (15 > 14), então `sgn(σ) = −1`, e `d = 0`, o que dá invariante `−1`. No tabuleiro resolvido, o invariante é `+1`. Portanto, o estado resolvido nunca é alcançado.

## Como usar

Abra o arquivo `index.html` em qualquer navegador. Não há dependências, instalação nem acesso à internet.

## Como publicar no GitHub Pages

1. Crie um repositório e envie `index.html` e `README.md` para a branch `main`.
2. Abra **Settings → Pages**.
3. Em **Build and deployment**, escolha **Deploy from a branch**, branch `main` e pasta `/ (root)`.
4. Após alguns minutos, a página estará em `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/`.

## Estrutura

```
index.html   página única: simulador, explicação e estilos
README.md    este arquivo
```

## Referência

W. W. Johnson e W. E. Story, *Notes on the "15" Puzzle*, American Journal of Mathematics, 1879.

## Licença

Defina a licença do repositório (por exemplo, MIT para o código ou CC BY 4.0 para o material didático).
