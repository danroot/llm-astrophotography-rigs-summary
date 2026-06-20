# Using LLMs to Run Astrophotography Rigs

**Yes.** Hobbyists and researchers actively use LLMs (Gemini, ChatGPT, Claude, etc.) to help run astrophotography rigs—from sequencing/troubleshooting to direct hardware control and full autonomous observation pipelines.

## Hobbyist examples

- On Cloudy Nights, users feed rig specs (telescope, mount, camera, OAG), NINA sequencer JSON files, and horizon data to **Gemini**. It reviews for errors, suggests improvements, recommends targets/exposures/filters, and outputs importable JSON for direct use in NINA.

- **ChatGPT** parses PHD2 guiding logs from ASIAIR rigs, writes Python scripts to analyze/plot data for optimal dithering/drizzle stacking, and troubleshoots PixInsight processing for large stacked images from rigs.

## Direct hardware control

**LUNA firmware** (free, open) turns cheap ESP32 boards (~$5-10) into a Wi-Fi/MCP bridge for **Claude**. Natural language commands ("slew to M31", "nudge focuser") translate to LX200 commands for mounts (OnStep, etc.). It supports NINA via HTTP API, INDI, SkySafari/Stellarium, sensor monitoring (e.g., DHT22), and on-device Lua scripts for autonomous routines like periodic refocusing. Fits backyard or remote astro rigs.

## Research/full automation

**StarWhisper Telescope** (LLM agent framework, deployed since 2024) uses models like Qwen-2.5 to automate end-to-end observations on telescope arrays:

- Generates site-specific target lists.
- Controls telescopes via NINA + custom plugins + ASCOM (slewing, focusing, imaging).
- Runs real-time image analysis (astrometry, photometry, transient detection).
- Dynamically triggers follow-ups and updates plans.

It has detected real transients (e.g., supernovae candidates) and drastically cut planning time. Built around amateur-friendly tools like NINA, so adaptable beyond professional surveys.

Many also use LLMs for target planning, equipment advice, and processing pipelines (e.g., Claude + Siril plugins).

**Bottom line**: LLMs are already assisting or directly controlling rigs via software integration (NINA/ASCOM), scripting, and hardware bridges like LUNA/ESP32. Full agentic autonomy is emerging in both hobby and research settings.

Check Cloudy Nights threads, LUNA GitHub (OnStepNinja/LUNA), and the StarWhisper paper (arXiv) for setups and details.

## Sources

- [Effective uses of AI and LLMs in astrophotography - Cloudy Nights forum](https://www.cloudynights.com/forums/topic/987582-effective-uses-of-ai-and-llms-in-astrophotography/)
- [LUNA firmware: Control your telescope with Claude AI via ESP32 Wi-Fi bridge](https://github.com/OnStepNinja/LUNA) · [ScopeTrader coverage](https://scopetrader.com/using-claude-to-control-a-telescope-via-esp32/)
- [StarWhisper Telescope: an AI framework for automating end-to-end astronomical observations (arXiv)](https://arxiv.org/abs/2412.06412)