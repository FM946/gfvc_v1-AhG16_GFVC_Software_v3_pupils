
# This is GFVC Software_v3_pupils

We implemented the `JVET-AJxxxx` test code on the basis of [gfvc_v1-AhG16_GFVC_Software_v3](https://vcgit.hhi.fraunhofer.de/jvet-ahg-gfvc/gfvc_v1)

+ Download the `{eye}-checkpoint.pth.tar` and `Pupil-256.yaml` files to the path `./GFVC/Pupil/checkpoint/`.

+ You need to complete the GFVC algorithm configuration. See [gfvc_v1-AhG16_GFVC_Software_v3](https://vcgit.hhi.fraunhofer.de/jvet-ahg-gfvc/gfvc_v1) for details. The checkpoints of GFVC are available at [this link](https://portland-my.sharepoint.com/:f:/g/personal/bolinchen3-c_my_cityu_edu_hk/EjYwalnuH_BCgMNADN5UMBAB7QpUrVKhCbkNZfqhO_ZUcg?e=Bh0fEG)

+ Our **checkpoints** are available at [this link](https://drive.google.com/file/d/1CHdydhVDpBbHgy6f3_dWRpGMXlgYS18X/view?usp=sharing)

+ The overall testing sequences in **RGB444** domain is available at [this link](https://portland-my.sharepoint.com/:f:/g/personal/bolinchen3-c_my_cityu_edu_hk/En0W90hNlrZLokuzGb67lgIBMqeHSIZZHff95ZyI0-WG7g?e=1cx4ZG).

+ The overall testing sequences in **YUV420** domain is available at [this link](https://portland-my.sharepoint.com/:f:/g/personal/bolinchen3-c_my_cityu_edu_hk/Emy2k26BY1VKoeXwxTWlPtoB8Z6kM62g3eEl0uyyuKjLfQ?e=wFzKjn).

+ The specific implementaion and `training codes` of algorithms are in the subfolder `source`.

## How to run it

### python
```
python = 3.8
```

### Independence
```commandline
pip install -r requirements.txt
```

### Test
+ **Before starting the test**, make sure you already have the GFVC result. If not please set `gfvc_run = 'True'` in `./config/pupils.yaml`.
+ The code can be launched by running `python run_pupils.py --config ../config/pupils.yaml` under `source/` fold after specifying all setting in config under `config/pupils.yaml`.
+ And then you can get an **Excel** in `experiment/` fold, `SummaryAE.xlsx` or `SummarySEI.xlsx`, which contains bitsrate information.
+ The video can be found in `experiment/{gfvc_model}/{Iframe_format}/{feature_coding_mode}/pupil/dec/`.




### Functionalities 
+ **Arithmetic coding** and **Coding with SEI** are supported for pupils feature encoding. Please specify `feature_coding_mode` in config file as `AE` or `SEI`. For both coding methods, recommended quantization factors are given in provided config files by `qf_list`.

+ **Coding with SEI** supports both `adaptive` and `non-adaptive` modes. Adaptive means to determine whether the frame needs to transmit pupil information and set the flag bit adaptively.You can set `adaptive_list` as `['OFF', 'ON']`, `['ON']`or`['OFF']`in config file.
## BibTeX Reference
```
@inproceedings{JVET_AI0137,
            title={AHG9/AHG16: Update on Pupil position SEI message for Generative Face Video},
            author={F. Ma, A. Trioux, S. Gao, Y. Yao, F. Yang, F. Xing, Z. Wang},
            journal={The Joint Video Experts Team of ITU-T SG 16 WP 3 and ISO/IEC JTC 1/SC 29, doc. no. JVET-AI0137},
            year={2024}
          }	
@inproceedings{JVET_AI0047,
            title={AhG16: Higher-resolution Test Sequences and Test Results for Generative Face Video Compression},
            author={B. Chen, S. Yin, Y. Ye, R.-L. Liao, J. Chen, S. Wang},
            journal={The Joint Video Experts Team of ITU-T SG 16 WP 3 and ISO/IEC JTC 1/SC 29, doc. no. JVET-AI0047},
            year={2024}
          }		
@inproceedings{JVET_AI0156,
            title={AHG9/AHG16: On generative face video SEI messages.},
            author={J. Chen, B. Chen, Y. Ye, S. Yin, S. Wang, P. Yin, S. McCarthy, H.-B. Teo.},
            journal={The Joint Video Experts Team of ITU-T SG 16 WP 3 and ISO/IEC JTC 1/SC 29, doc. no. JVET-AI0156},
            year={2024}
          }		
@inproceedings{JVET_AH0109,
            title={AHG16: Removal of the analysis model on the decoder side and lightweight design},
            author={R. Zou, B. Chen, R.-L. Liao, J. Chen, Y. Ye},
            journal={The Joint Video Experts Team of ITU-T SG 16 WP 3 and ISO/IEC JTC 1/SC 29, doc. no. JVET-AH0109},
            year={2024}
          }		 
@inproceedings{JVET_AH0114,
            title={AHG 16: Updated Common Software Tools for Generative Face Video Compression},
            author={B. Chen, Y. Ye, G.Konuko, G. Valenzise, S. Yin, S. Wang},
            journal={The Joint Video Experts Team of ITU-T SG 16 WP 3 and ISO/IEC JTC 1/SC 29, doc. no. JVET-AH0114},
            year={2024}
          }
@inproceedings{JVET_AH0138,
            title={AHG9/AHG16: Pupil position SEI message for Generative Face Video},
            author={A. Trioux, Y. Yao, F. Ma, F. Yang, F. Xing, Z. Wang},
            journal={The Joint Video Experts Team of ITU-T SG 16 WP 3 and ISO/IEC JTC 1/SC 29, doc. no. JVET-AH0138},
            year={2024}
          }	
@inproceedings{JVET_AG2035,
            title={Test conditions and evaluation procedures for generative face video coding},
            author={S. McCarthy, B. Chen},
            journal={The Joint Video Experts Team of ITU-T SG 16 WP 3 and ISO/IEC JTC 1/SC 29, doc. no. JVET-AG2035},
            year={2024}
          }
@inproceedings{JVET_AG0042,
            title={AHG 16: Proposed Common Software Tools and Testing Conditions for Generative Face Video Compression},
            author={B. Chen, J. Chen, R.-L. Liao, Y. Ye, S. Wang},
            journal={The Joint Video Experts Team of ITU-T SG 16 WP 3 and ISO/IEC JTC 1/SC 29, doc. no. JVET-AG0042},
            year={2024}
          }
@inproceedings{JVET_AG0048,
            title={AHG16: Interoperability Study on Parameter Translator of Generative Face Video Coding},
            author={S. Yin, B. Chen, J. Chen, R.-L. Liao, Y. Ye, S. Wang},
            journal={The Joint Video Experts Team of ITU-T SG 16 WP 3 and ISO/IEC JTC 1/SC 29, doc. no. JVET-AG0048},
            year={2024}
          }  
```