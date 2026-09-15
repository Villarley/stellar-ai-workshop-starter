# 5 ideas de producto validadas contra el ecosistema Stellar

Cada idea se corrió por `scout.vetIdea` (competidores, madurez, financiamiento SCF, gap de oferta). Snapshot 2026-09-15. Complementa [tokenizacion-scf.md](tokenizacion-scf.md) y [tokenizacion-hackathon-oportunidades.md](tokenizacion-hackathon-oportunidades.md).

**Aviso de método:** `vetIdea` compara contra los proyectos "más cercanos" dentro de la vertical detectada, ponderados por los términos de la idea (`matchMode: vertical+scored` en los 5 casos) - no es una prueba de que un competidor haga exactamente lo mismo. Verifica manualmente antes de comprometerte con una idea.

---

### 1. Pase de compliance ZK reusable para RWA tokenizados
**Problema:** cada proyecto RWA en Stellar (Talwex, Pipeline, Liqvid, TERWA…) reconstruye su propio flujo de KYC/acreditación. En el hackathon "Real-World ZK" salieron al menos 4 prototipos aislados (BatchGuard, Pool Pass, NARTHEX, lumengate) resolviendo la misma pieza sin compartirla entre sí.
**Producto:** SDK/contrato Soroban que emite una credencial verificable con pruebas ZK ("KYC aprobado", "inversor acreditado") - al estilo de Chaincerts pero enfocado en RWA - integrable por cualquier emisor con pocas líneas, en vez de que cada uno construya su propio flujo.
**Evidencia:** vertical=RWA; competidores cercanos Brale, Bitbond, Lend, Rivool Finance (plataformas de compliance/tokenización, ninguno expone esto como capa reusable); 7 proyectos auditados en la vertical, 0 de los competidores mostrados con uso verificado en mainnet.

### 2. Vault de colateral componible para RWA en mercados de préstamo
**Problema:** activos RWA tokenizados son difíciles de usar como colateral DeFi por sus períodos de redención y regulación.
**Producto:** vault (al estilo de "Orion", prototipo de hackathon) que envuelve RWA permisionados y los expone como colateral componible para mercados de préstamo aislados, integrado con Blend u otro protocolo de lending existente.
**Evidencia:** esta es la idea MÁS saturada de las 5 - competidores directos ya en producción: Liqvid.xyz ($137.5K SCF), HiYield ($150K SCF), y Microvault (única con uso on-chain verificado y 20 en GitHub entre las mostradas). Solo tiene sentido con una cuña de diferenciación fuerte (tipo de activo o jurisdicción específica).

### 3. Agente de IA que gestiona yield de RWA de forma autónoma (micropagos x402)
**Problema:** los productos de yield RWA actuales (Ballast Re, For Yield, DeFindex) requieren que un humano decida cuándo entrar/salir de una posición.
**Producto:** agente que monitorea rendimiento entre vaults RWA/DeFi, rebalancea automáticamente, y paga sus propias consultas de datos/oráculos vía micropagos x402, sin custodiar fondos del usuario.
**Evidencia:** vetIdea lo mapea a la vertical AI, con competidores solo débilmente relacionados (Turbolong, XBid AI, Benji, Spiko) y apenas 1 repo con uso verificado en mainnet. La combinación específica "agente autónomo + yield RWA + x402" casi no tiene prior art shippeado - solo el prototipo de hackathon "continuum" la toca directamente.

### 4. Proof-of-reserves / solvencia como servicio para emisores de stablecoins y RWA
**Problema:** los emisores en Stellar publican solvencia manualmente o de forma trimestral (cuando la publican), un riesgo de confianza recurrente.
**Producto:** oráculo/servicio (al estilo del prototipo de hackathon "Crisp") que verifica continuamente on-chain que las reservas de un emisor superan sus pasivos, con pruebas ZK opcionales para no exponer montos exactos, ofrecido como servicio a cualquier proyecto de la vertical.
**Evidencia:** vertical=Stablecoin; competidores adyacentes (Talwex, Trustline, USDY, Circle) no ofrecen esto como servicio independiente - es pieza de infraestructura, no competencia directa. Solo 1 de los repos mostrados tiene uso verificado en mainnet.

### 5. Tokenización + off-ramp de stablecoin para commodities agrícolas en mercados emergentes
**Problema:** pequeños productores/comerciantes agrícolas en África/LatAm no tienen acceso a financiamiento de capital de trabajo vía tokenización - las plataformas de trade finance ya existentes (Pipeline, Airswift) apuntan a volúmenes institucionales más grandes.
**Producto:** plataforma que tokeniza inventario/cosecha como colateral, con off-ramp local a stablecoin (al estilo de Fonbnk para airtime, aplicado a agro) para dar liquidez inmediata al productor.
**Evidencia:** competidores adyacentes (Fonbnk, Credible, CryptoMate, Fundable) tocan on/off-ramp en mercados emergentes pero ninguno commodities agrícolas específicamente; el prototipo de hackathon "Afri Assets" (Nigeria) ya validó demanda de este ángulo sin llegar a financiamiento SCF.

## Recomendación para 20 minutos de pitch

De las 5, las **#1, #3 y #4** tienen menos competencia consolidada (0-1 repos con uso verificado en mainnet entre los comparables) y son piezas de infraestructura reusable, no otra app de tokenización - encajan mejor con la señal de "el hueco está en compliance/liquidez/confianza, no en tokenizar otro activo" que salió del análisis de gaps. La **#2 está más saturada**; la **#5 depende de validar demanda local real** antes de construir.
