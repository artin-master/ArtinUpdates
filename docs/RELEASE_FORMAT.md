# Formato oficial de Release — Artin Updates

## Convenção de tags

- Artin NetLens: `anl-vX.Y.Z`
- Artin RescNow: `arn-vX.Y.Z`

## Assets esperados

Para cada release de aplicativo, publicar:

1. Pacote principal (`.zip` ou `.tar.gz`)
2. Arquivo de checksum SHA-256 correspondente
3. Opcionalmente notas adicionais ou metadados

Exemplo ANL:

- `ArtinNetLens_0.15.1_linux.zip`
- `ArtinNetLens_0.15.1_linux.zip.sha256`

## Fluxo do atualizador

1. Consultar o manifesto do canal (`stable` ou `beta`).
2. Comparar a versão local com `version`.
3. Se houver versão mais nova, localizar o asset indicado.
4. Baixar para diretório temporário.
5. Calcular SHA-256 e comparar com o manifesto.
6. Criar backup da instalação atual.
7. Aplicar a atualização.
8. Reiniciar o aplicativo.
9. Em caso de falha, restaurar o backup anterior.

## Regras de segurança

- Nunca executar pacote cujo SHA-256 não corresponda ao manifesto.
- Nunca apagar dados persistentes do usuário durante atualização.
- Credenciais, inventário, sites, históricos e configurações devem permanecer fora do runtime substituído.
- Atualizações obrigatórias só podem ser usadas quando explicitamente definidas em `mandatory: true`.

## Estado inicial

O Artin NetLens parte da versão-base `0.15.0`. O primeiro teste real de atualização será `0.15.0 -> 0.15.1`.
