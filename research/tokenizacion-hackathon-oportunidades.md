# Qué problemas atacar con tokenización en un hackathon de Stellar

Datos vía Raven (Scout: `getClusters`, `analyzeEcosystem(dimension=gaps)`, `searchHackathonBuilds`). Snapshot generado el 2026-09-15. Complementa [research/tokenizacion-scf.md](tokenizacion-scf.md) (proyectos de tokenización ya financiados por el SCF).

- **La tokenización de RWA en general ya está saturada, no es whitespace.** El clúster de tipo `RWA` tiene el crowdedness score máximo (10/10): 94 proyectos activos, 52 financiados por SCF, $5.83M USD acumulados en fondos. Fuente: `scout.getClusters(dimension=types)`, stellarlight.xyz/directory, 2026-09-15.

- **El análisis de gaps lo confirma.** `scout.analyzeEcosystem(dimension=gaps)` mide qué verticales están "underbuilt" (≤3 proyectos) o "absent" en el directorio. RWA no aparece en ninguna de las dos listas - el único tipo señalado como underbuilt en todo el ecosistema es "Faucet" (2 proyectos). Conclusión práctica: el hueco no está en "tokenizar otro activo", está en resolver problemas transversales dentro de RWA (compliance, liquidez, interoperabilidad). Fuente: `scout.analyzeEcosystem`, 2026-09-15.

- **Track caliente ahora mismo: privacidad/compliance para RWA tokenizados.** El evento "Stellar Hacks: Real-World ZK" generó al menos 6 builds recientes atacando este ángulo, ninguno marcado todavía como ganador (señal de competencia activa y no resuelta):
  - *BatchGuard ZK* - liquidación privada de facturas del mundo real sin exponer montos. [dorahacks.io/buidl/46476](https://dorahacks.io/buidl/46476)
  - *Crisp* - oráculo ZK de proof-of-reserves/solvencia en tiempo real para emisores de stablecoins. [dorahacks.io/buidl/46117](https://dorahacks.io/buidl/46117)
  - *Nebula* - infraestructura de settlement privado para RWA tokenizados. [dorahacks.io/buidl/46469](https://dorahacks.io/buidl/46469)
  - *Pool Pass* - prueba ZK de "soy inversor elegible" sin exponer identidad ni patrimonio. [dorahacks.io/buidl/46442](https://dorahacks.io/buidl/46442)
  - *lumengate* - compliance con passkeys + ZK para settlement regulado. [dorahacks.io/buidl/46264](https://dorahacks.io/buidl/46264)
  - *NARTHEX* - KYC/AML con ZK para RWA sin exponer datos personales. [dorahacks.io/buidl/46248](https://dorahacks.io/buidl/46248)

  Fuente: `scout.searchHackathonBuilds(q="tokenization real world asset")`, 2026-09-15.

- **Ángulo de colateral/liquidez componible.** *Orion* (Scaffold Stellar Hackathon) convierte RWA permisionados en colateral componible que rinde yield para mercados de préstamo aislados - mismo problema que atacan proyectos ya financiados como Octarine (liquidez RFQ, $129.7K SCF) o HiYield, pero sin ganador claro todavía a nivel hackathon. Fuente: [dorahacks.io/buidl/36340](https://dorahacks.io/buidl/36340).

- **Ángulo agentes de IA + RWA (incipiente).** *continuum* (Stellar Hacks: Agents) explora agentes de IA autónomos que compran, venden y generan yield de activos del mundo real usando micropagos x402. Cruza dos verticales con alto crowdedness por separado (AI: 54 proyectos, RWA: 94) pero la intersección específica todavía tiene poco prior art. Fuente: [dorahacks.io/buidl/42705](https://dorahacks.io/buidl/42705).

- **Nicho geográfico/de activo sin cobertura SCF visible.** *Afri Assets* (Scaffold Stellar Hackathon, sin financiamiento SCF) tokeniza activos agrícolas en Nigeria - ni la geografía (África) ni ese tipo de commodity aparecen en los proyectos de tokenización ya financiados por SCF relevados en la investigación previa. Fuente: [dorahacks.io/buidl/36228](https://dorahacks.io/buidl/36228).

- **Si tu idea se parece a un proyecto ya financiado, vas a competir directo.** Untangled (crédito privado), Talwex (bonos), Splyce (yield RWA→DeFi), Pipeline (trade finance de commodities), Liqvid (activos alternativos privados), Spydra (tokenización low-code), Octarine (liquidez RFQ) y Verseprop (real estate) ya están en producción y financiados - revisa [research/tokenizacion-scf.md](tokenizacion-scf.md) antes de comprometerte con una idea similar.

## Notas y limitaciones

- El "gap" que mide `analyzeEcosystem` es de **oferta** (qué existe en el directorio), no de demanda real - un tipo puede estar bien cubierto en cantidad de proyectos y aun así tener espacio si la calidad/ejecución es floja.
- La ausencia de un proyecto de hackathon en un tema no prueba que nadie lo haya intentado antes; el índice de DoraHacks usado (`searchHackathonBuilds`) cubre ~1,348 builds indexados y la búsqueda usada tuvo 46 coincidencias, de las que se muestran 15.
- Ningún build de hackathon citado aquí fue verificado como ganador salvo que se indique explícitamente; "sin ganador" es una lectura de la data al 2026-09-15, no un juicio de calidad.
