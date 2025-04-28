# GWASKit-POS-to-RSID-Converter-Python-Version-
This is a lightweight Python script that replicates the POS-to-RSID conversion feature from GWASKit,
adapted for environments like Google Colab where RAM is limited.

✨ The script splits data by chromosome to optimize memory usage and handles batch processing of genomic data.

📌 Background
GWASKit is a powerful Linux-based toolset for genome-wide association studies (GWAS) data processing.
However, its native POS-to-RSID conversion feature requires a Linux system and large memory resources.

This project re-implements that feature in Python, making it accessible for Google Colab and similar platforms with limited RAM.

🚀 Features
🧬 Convert chromosome positions (CHR:POS) to rs IDs.

🗂️ Split large datasets by chromosome to manage memory efficiently.

🔁 Batch processing of multiple files automatically.

🛠️ Designed for low-RAM environments (e.g., Colab).
