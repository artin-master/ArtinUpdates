# AKDB Contribution Protocol v1

## Objetivo

Permitir que Artin NetLens, Artin RescNow e futuros aplicativos Artin contribuam com evidências técnicas reutilizáveis para evolução da Artin Knowledge Database (AKDB), sem promover dados locais diretamente para a base oficial.

## Fluxo

1. O aplicativo aprende localmente a partir de uma confirmação explícita do operador.
2. A candidata permanece local até ser revisada e marcada como aprovada.
3. O aplicativo gera um pacote minimizado e valida a fronteira de privacidade.
4. O pacote entra em uma fila local deduplicada.
5. O envio é opt-in e somente por HTTPS para um endpoint de ingestão configurado.
6. O serviço receptor coloca a contribuição em quarentena/revisão.
7. Somente contribuições revisadas podem ser convertidas em registros AKDB candidate/staging.
8. A promoção para AKDB stable é um processo separado, validado e versionado.

## Dados permitidos

- tipo de equipamento confirmado;
- prefixo OUI, nunca MAC completo;
- fabricante/OUI vendor;
- modelo e família anunciados;
- ONVIF hardware;
- SNMP sysObjectID;
- fabricante/modelo SSDP/UPnP;
- protocolos observados;
- serviços e portas TCP reutilizáveis;
- serviços SSDP e mDNS;
- quantidade de confirmações;
- pontuação de qualidade da revisão;
- versão da AKDB usada como base;
- aplicativo e versão que geraram o pacote.

## Dados proibidos

- endereço IP;
- MAC completo;
- hostname;
- nome do Site;
- SSID;
- serial, UDN ou identificadores equivalentes;
- usuário, senha, token, SNMP community ou qualquer credencial;
- conteúdo de tráfego, URLs visitadas ou payloads capturados.

## Schema lógico v1

```json
{
  "package_type": "artin-akdb-contribution",
  "schema_version": 1,
  "package_id": "akdbc-...",
  "generated_at": "ISO-8601",
  "generated_by": {
    "application": "Artin NetLens",
    "version": "0.15.3"
  },
  "base_database_version": "...",
  "privacy": {
    "contains_ip_addresses": false,
    "contains_full_mac_addresses": false,
    "contains_hostnames": false,
    "contains_serials_or_udn": false,
    "contains_site_names": false,
    "contains_credentials": false
  },
  "candidates": [
    {
      "review_state": "approved",
      "confirmation_count": 1,
      "review_quality": 0,
      "signature": {
        "confirmed_type": "..."
      }
    }
  ]
}
```

## Segurança do receptor

O receptor nunca deve confiar na declaração `privacy` do cliente. Deve validar novamente schema, tamanho, limites, campos proibidos, conteúdo inesperado e duplicação. Pacotes recebidos nunca entram diretamente em `stable`.

O endpoint deve usar HTTPS. Tokens de conta GitHub não devem ser embutidos nos aplicativos Artin.
