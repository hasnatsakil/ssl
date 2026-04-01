cat > create_mapping.py << 'EOF'
import pandas as pd
import os
from glob import glob


reports_root = "C:\Users\docXt\Desktop\research\ssl\mimic-cxr-dataset\mimic-cxr-reports\files"

print("Scanning reports...")
reports_list = []

for txt_path in glob(os.path.join(reports_root, "**", "s*.txt"), recursive=True):
    try:
        with open(txt_path, 'r', encoding='utf-8', errors='ignore') as f:
            report = f.read().strip()
        
        filename = os.path.basename(txt_path)          # e.g. s50414267.txt
        study_id = int(filename[1:-4])                 # remove 's' and '.txt'
        
        reports_list.append({'study_id': study_id, 'report': report})
    except:
        continue

df = pd.DataFrame(reports_list)
df = df.sort_values('study_id').reset_index(drop=True)

df.to_csv('reports_with_study_id.csv', index=False)
print(f"✅ Created reports_with_study_id.csv with {len(df)} reports")
print("First few rows:\n", df.head())
EOF

python create_mapping.py