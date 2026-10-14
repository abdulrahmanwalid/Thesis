# tleap inputs

Reconstructed tleap inputs for each simulation system (originally typed interactively).
Run with `tleap -f <file>.in`.

| File | System |
|---|---|
| `sox_baseline.in` | SOX + DNA + Mg2+ |
| `sox_ptr253.in` | SOX with phosphotyrosine 253 |
| `sox_ad51_mgsite.in` | SOX + AD51 at the Mg2+ site (also neutral/negative poses) |
| `sox_ad51_thr189.in` | SOX + AD51 at the Thr189/Tyr243 site |
| `ul12_dna.in` | UL12 homology model + DNA + Mg2+ |

Force fields: ff14SB (protein), phosaa14SB (PTR), OL15 (DNA), GAFF2/AM1-BCC (AD51), TIP3P water.

## Ion counts (SPLIT method)

Ions follow the SPLIT method (Machado & Pantano, 2020) for 0.15 M NaCl:

1. Run the file once up to `solvatebox` and note the number of waters (N_w) and the system charge (Q) from `charge`
2. N0 = 0.15 × N_w / 56
3. Na+ = round(N0 − Q/2), Cl− = round(N0 + Q/2)
4. Put these into `addionsrand` and run the full file
