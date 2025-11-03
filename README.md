# Academic Research Project
## Evaluation of Different Approaches to Medical Text Anonymization in Spanish

This project evaluates and compares different approaches for Named Entity Recognition (NER) in Spanish medical documents, using four specialized datasets and three types of models.

## Project Structure

### Datasets (`Datasets/`)
Contains four annotated medical datasets in BRAT format:

- **MEDDOCAN**: 1,000 medical documents (500 train, 250 dev, 250 test)
- **SPG**: 1,000 documents obtained from the Synthetic Patient Generator module (500 train, 250 dev, 250 test)  
- **SPGExtended**: 448 extended SPG documents (358 train, 45 dev, 45 test)
- **CARMEN-I**: 1,697 clinical case documents (847 train, 425 dev, 425 test)

Each dataset includes `.txt` (text) and `.ann` (annotation) files in BRAT format.

### Note about CARMEN-I
Due to licensing reasons, everything related to CARMEN-I is not public in this repository. The dataset can be accessed through PhysioNet: https://physionet.org/content/carmen-i/1.0.1/

### Models (`Models/`)
Implementation and evaluation of three different approaches:

##### 1. **REGEX** - Symbolic rules based on domain knowledge using regular expressions
- Pattern and rule-based approach
- Python implementation with text processing
- Execution files in each subfolder (`ejecucion.md`)

##### 2. **BiLSTM-CRF** - Recurrent Neural Network
- Deep learning model with BiLSTM + CRF architecture
- Based on word embeddings and context

##### 3. **Llama3.1** - Large Language Model
- Uses Llama 3.1 model for NER
- Implementation with prompts (one-shot)
- Direct evaluation on the datasets

## Results
Results are located in the `Results/` folder:

### Quantitative Metrics
- **`results_dev.xlsx`**: Evaluation metrics on development set
- **`results_test.xlsx`**: Evaluation metrics on test set
- Contains detailed metrics (Precision, Recall, F1-Score) by model and dataset

### Visualizations
- **`plots_dev/`**: Confusion matrices and plots for development set
- **`plots_test/`**: Confusion matrices and plots for test set
- Visual comparison between models (REGEX, BiLSTM-CRF, Llama3.1)

## Execution

To run specific evaluations, refer to the `ejecucion.md` files in each model:
- `Models/REGEX/[dataset]/ejecucion.md`
- `Models/BiLSTM-CRF/ejecucion.md` 
- `Models/Llama3.1/[dataset]/ejecucion.md`

To generate global confusion matrices:
```bash
cd Models/Scripts
python3 confusion_matrix_generator_global.py [MODEL] --partition [dev/test/both]
```

## License

This project is licensed under **CC0 1.0 Universal** (Creative Commons Zero) - see the [LICENSE](LICENSE) file for more details.

The CC0 license allows free use, modification and distribution of the code without restrictions, effectively dedicating the work to the public domain.
