# Artin NetLens 0.15.3 — AKDB Contribution Pipeline

## Objetivo

Adicionar o primeiro pipeline oficial de contribuição dos aplicativos para evolução da AKDB, mantendo revisão humana e fronteira de privacidade.

## Principais mudanças

- fila local deduplicada de contribuições AKDB;
- somente candidatas aprovadas localmente entram no pacote;
- sanitização obrigatória para impedir IPs, MAC completo, hostnames, Sites, seriais/UDN e credenciais;
- novo painel `Configurações → AKDB / Base de conhecimento → Contribuições`;
- opt-in explícito para envio;
- transporte HTTPS genérico preparado para endpoint de ingestão;
- nenhuma credencial GitHub embutida no aplicativo;
- contribuições recebidas devem entrar em revisão/quarentena e nunca promover diretamente para `stable`;
- exportação manual JSON e aprendizado local existentes permanecem disponíveis.

## Pacote

`ArtinNetLens_0.15.3_akdb_contribution_pipeline.zip`

SHA-256:

`4ff15192567ae3b6271b622153822847148f369ae0ed1903814946e1e063af6a`

## Validação

- 407 testes automatizados aprovados;
- `compileall` aprovado;
- ZIP validado sem erros.

## Observação sobre envio online

A 0.15.3 implementa o cliente, a fila, a sanitização, o opt-in e o contrato HTTPS. O envio efetivo para uma central Artin depende da implantação de um endpoint de ingestão compatível com `docs/AKDB_CONTRIBUTION_V1.md`. Sem endpoint configurado, os pacotes permanecem apenas na fila local.
