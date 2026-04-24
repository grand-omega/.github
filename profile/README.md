# Grand Omega

Independent R&D building focused, single-purpose AI tools — generative imaging
and sports analytics, each designed to run on hardware you already own.

---

## Project ZUN — Local AI Outfit & Image Editor

A complete, self-hosted stack for instruction-driven and mask-based image
editing. Runs on a single consumer GPU (**RTX 4070 Ti Super, 16 GB VRAM**).
From photo to finished edit in roughly **7 seconds** per job.

**Two inference tracks, one workflow driver:**

| Track | What it's for | Speed |
|---|---|---|
| **FLUX.1 Fill** | Mask-based inpainting with auto-masking (GroundingDINO + SAM). Strongest identity preservation. | Standard |
| **FLUX 2 klein** | Maskless, instruction-driven editing with a 4B-parameter model. Primary track. | 5–6× faster |

**What you get:**
- Custom-outfit editing with trained subject LoRAs
- Full LoRA training pipelines for both FLUX.1 and FLUX 2 (ai-toolkit + musubi-tuner)
- JoyCaption-based dataset prep tooling
- A clean HTTP API and a native mobile client — use it from your couch

### The three repositories

<table>
<tr>
<td width="33%" valign="top">

**[project-zun](https://github.com/grand-omega/project-zun)**

The ML core. ComfyUI workflows, training configs, dataset prep, and inference
recipes. FLUX.1 Fill + FLUX 2 klein. LoRA training on a single 16 GB GPU.

`Python` · `ComfyUI` · `FLUX`

</td>
<td width="33%" valign="top">

**[zun-rust-server](https://github.com/grand-omega/zun-rust-server)**

The API layer. A single-user Rust server wrapping ComfyUI with job
orchestration, SQLite persistence, crash recovery, and a health-monitored
HTTP API. LAN or Tailscale — no public exposure required.

`Rust` · `axum` · `sqlx` · `tokio`

</td>
<td width="33%" valign="top">

**[zun-android-app](https://github.com/grand-omega/zun-android-app)**

The client. A high-performance Android app optimized for the **Samsung Galaxy
Z Fold 7** — dynamic two-pane layouts, biometric lockout, immersive zoomable
photo viewer, encrypted credential storage.

`Kotlin` · `Jetpack Compose`

</td>
</tr>
</table>

### Design philosophy

- **Local-first.** Your photos never leave your network.
- **Single-user, self-hosted.** No multi-tenant complexity, no cloud bills.
- **Consumer hardware.** One GPU. One phone. One workstation.
- **Shippable is small.** The entire orchestrated system reconstructs from ~100 KB of config and source.

---

## Project Matrie — AI for Competitive Fencing *(in development)*

An AI analysis tool purpose-built for competitive fencers and their coaches.
Matrie ingests bout footage and extracts the things that actually matter on
the strip — tempo, distance, action sequences, decision patterns — so athletes
can review competitions with clarity instead of hours of manual tagging.

**Currently in active development.** Repository coming soon.

*If you're a fencer, coach, or club interested in early access, watch this
organization.*

---

## Contact

For questions or collaboration, please open an issue on the relevant
repository.
