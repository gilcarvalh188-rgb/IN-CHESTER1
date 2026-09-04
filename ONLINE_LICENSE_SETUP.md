# Licenca online — IN CHESTER

A tela de login agora valida a chave fora do aparelho, em segundo plano, usando HTTPS.

## Endpoints
- Pagina para obter a chave: https://ninjaarashi69.github.io/NinjaPlus/steps.html
- Lista de chaves ativas: https://ninjaarashi69.github.io/NinjaPlus/keys.txt

## Publicacao no GitHub Pages
Coloque o arquivo `NinjaPlus/keys.txt` na pasta publicada pelo GitHub Pages do projeto que atende `ninjaarashi69.github.io/NinjaPlus/`.

Formato:
```text
# comentarios sao ignorados
inchester
OUTRA-KEY-ATIVA
```

Uma chave por linha. Linhas vazias e linhas iniciadas por `#` sao ignoradas.

## Fluxo do aplicativo
1. O usuario toca em `OBTER CHAVE` e abre a pagina `steps.html`.
2. O usuario digita a chave recebida.
3. `ATIVAR LICENCA ONLINE` consulta `keys.txt` por HTTPS em uma thread separada.
4. Chave encontrada = acesso liberado e a licenca local e marcada como ativa.
5. Chave inexistente, servidor indisponivel ou erro de rede = acesso nao e liberado durante a ativacao.

## Observacao de seguranca
GitHub Pages e hospedagem estatica. O arquivo `keys.txt` fica publico, portanto esta solucao e adequada para um sistema simples de distribuicao/ativacao, mas nao e um backend secreto. Para revogacao forte, limites por dispositivo, expiracao, assinatura e protecao contra copia, substitua `LICENSE_API` por uma API HTTPS propria.
