# Artin NetLens 0.15.2 — Online Update Delivery

Primeira release preparada para validar o fluxo real de atualização on-line do Artin NetLens.

## Alterações

- Atualização on-line via repositório público `artin-master/ArtinUpdates`.
- Tags compartilhadas com prefixo `anl-v`, ignorando releases do Artin RescNow.
- Validação obrigatória por SHA-256 antes da instalação.
- Preservação de um atalho válido já existente na Área de Trabalho durante atualizações, evitando perder o estado de confiança do KDE/Plasma por simples regravação do `.desktop`.
- Backup transacional e confirmação explícita mantidos antes da aplicação da atualização.

## Assets esperados

- `ArtinNetLens_0.15.2_online_update_delivery.zip`
- `ArtinNetLens_0.15.2_online_update_delivery.zip.sha256`

## Tag

`anl-v0.15.2`
