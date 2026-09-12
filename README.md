# Artin Updates

Repositório público oficial para distribuição de atualizações dos aplicativos Artin.

## Aplicativos atendidos

- Artin NetLens (ANL)
- Artin RescNow (ARN)
- AKDB / Base de conhecimento compartilhada (futuro)

## Canais

- `stable`: versões estáveis aprovadas
- `beta`: versões de teste / pré-lançamento

## Convenção de tags

- ANL: `anl-vX.Y.Z`
- ARN: `arn-vX.Y.Z`

## Estrutura

- `manifests/anl-stable.json`
- `manifests/anl-beta.json`
- `manifests/arn-stable.json`
- `manifests/arn-beta.json`
- `docs/RELEASE_FORMAT.md`

Os pacotes binários devem ser publicados como assets de GitHub Releases. Os manifests apontam para a versão, tag, asset e hash SHA-256 correspondentes.
