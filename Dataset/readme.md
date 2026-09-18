# Dataset Folder

This folder contains the dataset files generated at each stage of the thyroid recurrence prediction workflow. The dataset preparation follows a step-wise transformation from the original clinical dataset to the final automata-enhanced dataset.

## Files

| File Name | Description |
|---|---|
| `Step_1_Original_Dataset.xls` | Original thyroid recurrence dataset containing clinical features and the target variable. |
| `Step_2_After_PDA_8_Features.xls` | Dataset obtained after applying Pushdown Automata (PDA)-based feature engineering. This stage adds eight PDA-derived features. |
| `Step_3_After_TM_5_Features.xls` | Dataset obtained after applying Turing Machine (TM)-based feature engineering on the PDA-updated dataset. This stage adds five TM-derived features. |
| `Step_4_Final_Automata_Enhanced_Dataset.xls` | Final automata-enhanced dataset containing original, PDA-derived, and TM-derived features. |
| `readme.md` | Description of dataset files and their role in the workflow. |

## Dataset Transformation Flow

```text
Step_1_Original_Dataset.xls
        ↓
Step_2_After_PDA_8_Features.xls
        ↓
Step_3_After_TM_5_Features.xls
        ↓
Step_4_Final_Automata_Enhanced_Dataset.xls
```

## PDA-Based Feature Engineering

The PDA stage creates eight structured features from the original clinical attributes. These features represent clinical hierarchy and encoded disease-state information. The PDA-derived features include level-based encodings and burden-based clinical representations.

Expected PDA-derived features include:

- `T_level`
- `N_level`
- `M_level`
- `Stage_level`
- `Risk_level`
- `Response_level`
- `TNM_Burden`
- `Hierarchy_Score`

## TM-Based Feature Engineering

The TM stage creates five additional features using transition-based and state-based logic. These features represent recurrence progression, state transition, and accept-state scoring.

Expected TM-derived features include:

- `Stage_Risk_Gap`
- `Progression_Flag`
- `Accept_State_Score`
- `Transition_Code`
- `State_ID`

## Scenario Usage

### Scenario I: Original Dataset

Uses:

```text
Step_1_Original_Dataset.xls
```

This scenario evaluates machine learning models using only the original clinical features.

### Scenario II: Automata-Enhanced Dataset

Uses:

```text
Step_4_Final_Automata_Enhanced_Dataset.xls
```

This scenario evaluates machine learning models using original features along with PDA- and TM-derived automata features.

## Target Variable

The target variable is:

```text
Recurred
```

It represents whether thyroid cancer recurrence occurred or not.

## Notes

- Do not manually edit intermediate dataset files unless the complete feature-engineering workflow is rerun.
- The final dataset should be generated from the original dataset through PDA and TM feature-engineering steps.
- Use the same target column name across all dataset files to avoid training errors in the ensemble notebook.
- If the file extension is changed from `.xls` to `.csv` or `.xlsx`, update the file paths in the notebooks accordingly.
