python -c '
import pandas as pd
mapping = pd.read_csv("reports_with_study_id.csv")
labeled = pd.read_csv("mimic-cxr-chexpert-labeled.csv")

final = pd.concat([mapping[["study_id"]], labeled], axis=1)
final.to_csv("mimic-cxr-chexpert-final.csv", index=False)
print("✅ Final file ready: mimic-cxr-chexpert-final.csv")
print("Columns:", final.columns.tolist())
'