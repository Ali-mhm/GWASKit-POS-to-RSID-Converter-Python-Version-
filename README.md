# GWASKit-POS-to-RSID-Converter-Python-Version-
This is a lightweight Python script that replicates the POS-to-RSID conversion feature from GWASKit,
adapted for environments like Google Colab where RAM is limited.

✨ The script splits data by chromosome to optimize memory usage and handles batch processing of genomic data.

# 📌 Background
GWASKit is a powerful Linux-based toolset for genome-wide association studies (GWAS) data processing.
However, its native POS-to-RSID conversion feature requires a Linux system and large memory resources.

This project re-implements that feature in Python, making it accessible for Google Colab and similar platforms with limited RAM.

# 🚀 Features
🧬 Convert chromosome positions (CHR:POS) to rs IDs.

🗂️ Split large datasets by chromosome to manage memory efficiently.

🔁 Batch processing of multiple files automatically.

🛠️ Designed for low-RAM environments (e.g., Colab).

# 📚 How to use this pipeline
**1. Install GWASkit:**
```
!wget https://github.com/Li-OmicsLab-MPU/GWASkit/releases/download/v1.0.0/GWASkit-1.0.0-amd64_linux.zip
!unzip GWASkit-1.0.0-amd64_linux.zip
!%cd GWASkit-1.0.0/
!chmod a+x ./GWASkit
```

**2. Download the GRCh37/38 rsdb:**
   ```
 !wget https://figshare.com/ndownloader/files/48635851 -O GRCh37.zip
 !unzip GRCh37.zip
   ```

**3. Download or clone this repository:**
```
#Clone the repository
git clone https://github.com/YOUR_USERNAME/GWASKit-POS-to-RSID-Converter-Python-Version.git
cd GWASKit-POS-to-RSID-Converter-Python-Version
```

**4. Example usage:**
4.1.  Define the column mapping for your data (this can be customized based on your data's column names)
 ```
from pos2rs_wrapper import pos2rs_pipeline

column_mapping = {
    'chromosome': 'chr',         # Name of the chromosome column
    'position': 'pos',           # Name of the base-pair position column
    'reference': 'ref',          # Name of the reference allele column
    'alternate': 'alt'           # Name of the alternate allele column
}
```
4.2. Run the pipeline
```
pos2rs_pipeline(
    input_file='your_data.csv',                    # Input CSV file
    gwaskit_path='/content/GWASkit-1.0.0/GWASkit',  # Path to GWASkit executable
    rsdb_path='/content/GRCh37',                    # Path to rsdb (GRCh37)
    column_mapping=column_mapping,                  # Column name mapping
    output_filename='final_output.csv'              # Optional: specify output file name
)
```
This will:

1. Split your data by chromosomes

2. Convert position to RSID

3. Merge all results into one CSV file!

# ✨ Credits
Built using GWASkit by Li-OmicsLab(https://github.com/Li-OmicsLab).
