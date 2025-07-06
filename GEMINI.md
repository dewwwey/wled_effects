# WLED Effects Project Setup

This project is for creating custom effects for a WLED LED ring.

## Initial Setup (July 6, 2025)

1.  **Git Initialization:** A Git repository was initialized in the project directory.
2.  **GitHub Repository:** The project is linked to the GitHub repository `https://github.com/dewwwey/wled_effects.git`.
3.  **Python Environment:** `uv` is used for dependency management and virtual environments.

## Troubleshooting Notes

*   **WLED API Communication:** Initial attempts to communicate with the WLED device via Python `requests` and `curl` faced issues, likely due to incorrect JSON payload formatting or network timeouts. A simpler `urllib.request` approach was attempted.
*   **Rust Library (`wled-json-api-library`):** Cloning and building this library revealed `serde` deserialization errors due to type mismatches between the library's Rust structs and the WLED API's JSON response (version 0.15.0). Specifically, `bool` values were being received where `u8` was expected in fields like `on` (in `cfg_def.rs`) and `seqskip` (in `cfg_if2.rs`).

## Next Steps

*   Re-establish reliable communication with the WLED device.
*   Develop custom effects using either Python or Rust, depending on the chosen approach.
