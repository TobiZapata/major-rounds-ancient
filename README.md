# Major rounds: Ancient

Versioned replay data for the Major MVP CS simulator.

`v1.0.0` contains 971 eligible Ancient rounds from 50 unique demos (50 source
files), sampled at 8 Hz plus action ticks. Of these, 902 rounds have equipment
supported by the assembler and matching derived metrics and resolutions.

## Files

- `v1.0.0/index.json`: eligible round catalog.
- `v1.0.0/economy-index.json`: catalog with equipment evidence and compatibility.
- `v1.0.0/round-metrics-v1.json.gz`: derived player metrics.
- `v1.0.0/round-resolution-v1.json.gz`: resolution-time statistics and equipment.
- `v1.0.0/demos/<sha256>/rNNN.json.gz`: compressed per-round telemetry.

Published root: https://tobizapata.github.io/major-rounds-ancient/v1.0.0/

Catalog references keep the application prefix `/round-bank-ancient/`. Consumers
map that prefix to this fixed Pages root and load selected rounds on demand.
The version directory and Git tag are immutable. Publish changed banks under
a new version and preserve older versions for saved games.

## Provenance

The laboratory classified 1,040 rounds; 69 were excluded from this published
bank. Reasons include incomplete postround tails (47), friendly fire (15),
missing opening weapons (9) and world deaths (3). Twenty-two additional rounds
from `spirit-vs-g2-m1-ancient-p1/p2.dem` were rejected for lacking five actors
per side and omitted from the catalog. Duplicate source files are deduplicated
by SHA-256, not their names.

Catalogs retain source demo filenames, hashed demo IDs, Steam IDs, round timing
and results. Replays contain positions, inventories and events needed for
playback. Original `.dem` files are not uploaded. This repository does not
assert ownership of the matches, demos or third-party identities; the source
material's attribution and redistribution terms still apply.

All replay checksums, end-state actor totals and inventories were validated
before import. The bank uses demoparser2 0.42.2. The extraction assumes 64 ticks/s;
buy labels describe weapon composition rather than money spent or player intent.
