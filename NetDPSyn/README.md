# NetDPSyn: Synthesizing Network Traces under Differential Privacy

## Introduction

This repository contains code for the paper: NetDPSyn: Synthesizing Network Traces under Differential Privacy. NetDPSyn is the first system to synthesize high-fidelity network traces under privacy guarantees. This work is developed under the [UCI DSP Lab](https://faculty.sites.uci.edu/zhouli/research/).

## Experimental setup
1. Clone this repo from the GitHub.

        git clone https://github.com/DanyuSun/NetDPSyn.git

1. Download the raw datasets from [here](https://drive.google.com/drive/folders/1MHRJxLhnJWZln8XBCon9UrN_EwVj14BE). And save them in `./temp_data/raw_data/` folder.

2. Your directory structure should look like this:

        NetDPSyn
           └── temp_data
                   └── raw_data
                        └── caida.csv
                        └── cidds.csv
                        └── dc.csv
                        └── ton.csv
                        └── ugr16.csv
           └── exp
           └── ...

4. **Note:** Please ensure all paths in `config_dpsyn.py` are updated to reflect your local directory structure. Additionally, you can adjust parameters in `parameter_parser.py` as needed.


## Usage

1. **Preprocess Data**. Run `lib_preprocess/preprocess_network.py`. This will generate a preprocessed pickle file in the `temp_data/processed_data` folder, along with a mapping for binning. Additionally, a trivially decoded CSV file (binning and unbinning) will be created in the `temp_data/synthesized_records` folder.

        python preprocess_network.py


2. **Synthesize Data**. Next, run `main.py` to generate the synthesized data. The synthesized data will be saved in the `temp_data/synthesized_records` floder.

        python main.py


3. **Downstream Tasks**. You can run code from `lib_downstream` (e.g., `lib_downstream/ml_tasks.py`). This will print out the evaluation results for both the raw dataset and the synthesized dataset.

        python ml_tasks.py


## Citation
If you find our work useful for your research, please consider citing the paper: 
```
@misc{sun2024netdpsynsynthesizingnetworktraces,
      title={NetDPSyn: Synthesizing Network Traces under Differential Privacy}, 
      author={Danyu Sun and Joann Qiongna Chen and Chen Gong and Tianhao Wang and Zhou Li},
      year={2024},
      eprint={2409.05249},
      archivePrefix={arXiv},
      primaryClass={cs.CR},
      url={https://arxiv.org/abs/2409.05249}, 
}
```


