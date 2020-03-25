# MobiCom 2020, Paper #382

### This is an anonymized Github repository for the submitted paper "NEMO: Enabling Neural-enhanced Video Streaming on Commodity Mobile Devices".


### 1. DNN Specifications (cited in Section 5.3, "Providing multiple options")

NEMO uses multiple quality DNNs (Low, Medium, High) whose architecture is described in the below figure.

Each residual block consists of two convolution layer, one ReLU layer, and one element-wise summation layer (e.g., Conv-ReLU-Conv-Sum)

<img src="https://user-images.githubusercontent.com/62630456/77510739-cb2a4300-6eb2-11ea-8ae0-2795939b4c8f.png" width="90%"></img>

The below table specifies the numbers of residual blocks and the number of channels of convolution layers for each quality DNN.

|  Resolution   | Quality | Number of residual blocks | Number of channels |
|:-------------:|:-------------:|:-------------:|:-----:|
| 240p      | Low      | 8 | 9 |
| 240p      | Medium      | 8 | 21 |
| 240p      | High      | 8 | 32 |
| 360p      | Low      | 4 | 8 |
| 360p      | Medium      | 4 | 18 |
| 360p      | High      | 4 | 29 |
| 480p      | Low      | 4 | 4 |
| 480p      | Medium      | 4 | 9 |
| 480p      | High      | 4 | 18 |

### 2. DNN quality to Device Mapping (cited in Section 7, "Baseline")

NEMO selects different quality DNNs depending on videos and devices (refer Section 5.3, "Adapting to Devices and Contents").

The below table desribes the mapping from DNN qualities to our local mobile devices including Xiaomi Redmi Note 7 (Entry-level), Xiaomi Mi9 (High-end), and LG Gpad5 (Tablet).

#### a. 240p to 1080p

|  Content  | Xiaomi Redmi Note7 | Xiaomi Mi9 | LG Gpad 5 |
|:-------------:|:-------------:|:-------------:|:-----:|
| Product review  | Low | Medium | High | 
| How-to      | Low | High | Medium |
| Vlogs      | Low | Medium | Low |
| Game play  | Low | High | Medium |
| Skit      | Low | Medium | Low | 
| Haul      | Low | Medium | Low |
| Challenges      | Low | High | High |
| Favoriate      |  Low | Medium | Low |
| Education      | Low | Medium | Low |
| Unboxing      | Low | High | Medium |

#### b. 360p to 1080p

|  Content  | Xiaomi Redmi Note7 | Xiaomi Mi9 | LG Gpad 5 | 
|:-------------:|:-------------:|:-------------:|:-----:|
| Product review      | Low | Medium | Medium |
| How-to      | Low| High | Medium |
| Vlogs      | Low | Low | Low |
| Game play  | Low| Medium | Medium | 
| Skit      | Low | Low| Low |
| Haul      | Low| Low| Low|
| Challenges      | Low | High | Medium |
| Favoriate      | Low | Low | Low |
| Education      | Low | Low | Low |
| Unboxing      | Low | Low | Low |

#### c. 480p to 1080p

|  Content  | Xiaomi Redmi Note7 | Xiaomi Mi9 | LG Gpad 5 | 
|:-------------:|:-------------:|:-------------:|:-----:|
| Product review      | Low | High | Medium |
| How-to      | Low | High | Medium |
| Vlogs      | Low | Low| Low|
| Game play  | Low | Medium | Medium |
| Skit      | Low | Low| Low|
| Haul      | Low | Low| Low|
| Challenges      | Low| Medium| Medium|
| Favoriate      | Low | Medium | Medium |
| Education      |Low | Medium | Medium |
| Unboxing      |Low | Medium| Medium|

### 3. Dataset (Video, Network traces)

NEMO uses two types of datasets: 1) Video to train super-resolution DNNs, 2) Network traces to test adaptive streaming.
We provide them at `dataset`.

### 4. Demo videos

NEMO significantly improves video quality by super-resolution. 

To demonstrate this, we provide three sample videos at `demo`.
