# 2VecIR
Doc2vec, formula2vec, and 2VecIR models and empirical results for using text and formula vectors to rank answers to math questions.

## Repository Structure
- Word2vec: where code for all of the models are stored
  Contains bash scripts and a requirements file.  Run `before_run.sh` to generate a python environment and download requirements.  The other bash scripts run the different models, one for doc2vec (`run_venv_doc2vec.sh`), another for formula2vec (`run_venv_formula2vec.sh`), and one for 2VecIR (`run_venv_doc2vec_form2vec.sh`).  There are 5 different modes: train, assess, test, eval, and metrics, but since 2VecIR is composed of doc2vec and formula2vec there is not an option to train, but requires checkpoint instances of those trained models.
  - doc2vec: where source code is stored
     Contains python programs for creating and running doc2vec, formula2vec, and 2VecIR.
    - checkpoints: where checkpoints for the model are saved to
        - d2v_CBOW: where checkpoint for pretrained doc2vec model is stored
        - f2v_CBOW: where checkpoint for pretrained formula2vec model is stored
  - experimental_results: where results for training and running the models are stored
    `d2v_f2v_metrics.xls` contains results for running the models on each question and averaged on all of the questions.  `d2v_f2v_metrics_full_excel.txt` contains results from a run of the 2VecIR model on the MSE dataset, and also contains the total number of questions and answers.
      - Figures: figures used to depict the results of the models run on the MSE dataset
      - Results: the output and results from running on the models
      - SampleQAs: data from the MSE dataset sampled and processed to be easier to interpret
