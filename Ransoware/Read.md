# Simulação de Ransomware em Python

Este é um projeto prático desenvolvido para o desafio de Cibersegurança da DIO. A ideia foi programar um ransomware básico do zero usando Python, para entender na prática como a criptografia bloqueia o acesso aos arquivos.

> ⚠️ **Aviso:** Este código foi feito estritamente para fins educacionais e executado em um ambiente controlado (apenas em uma pasta de testes local).

## Como o código funciona
Utilizei a biblioteca `cryptography` (módulo Fernet) do Python para gerar uma chave de criptografia simétrica. O script `ransoware.py` foi programado para varrer uma pasta específica (`test_files`), ler o conteúdo dos arquivos e reescrevê-los de forma criptografada. No final, ele ainda gera um arquivo `.txt` com uma mensagem simulando um pedido de resgate.

## O ataque na prática (Antes e Depois)

Para demonstrar o impacto, criei alguns arquivos com dados fictícios (como senhas e CPFs). Veja como eles eram lidos antes de rodar o script:

![Arquivos antes do ataque](antes.png)
*Arquivos originais e legíveis na pasta de testes.*

Logo após a execução do código, o conteúdo original é totalmente substituído por um texto cifrado. Sem a chave gerada pelo programa, é impossível recuperar a informação:

![Arquivos criptografados](depois.png)
*Arquivos bloqueados pela criptografia e a nota de resgate gerada.*

## Como se defender?
Entender como a ameaça funciona é o primeiro passo para a defesa. No mundo real, as melhores práticas contra ransomwares incluem:
1. **Backup offline:** Manter cópias de segurança em um HD externo ou nuvem que não fique sincronizando o tempo todo. Se o sistema for infectado, o ransomware não alcançará o backup desconectado.
2. **Antivírus e EDR:** Soluções de segurança modernas conseguem notar quando um processo estranho começa a alterar dezenas de arquivos simultaneamente e o interrompem antes que ele termine.
3. **Atenção ao Phishing:** A porta de entrada para a maioria dos malwares é o erro humano, como clicar em links suspeitos ou baixar anexos falsos por e-mail. A conscientização é a primeira barreira.
