# Highly Semantic Vision-Language Benchmarks #

## Popular QA ##
### 1. VCR ###
#### a. Description ####
Visual Commonsense Reasoning. It is consisted of 290k multiple choice QA problems derived from 110k movie scenes. For every image, there are two types of questions asked. The first (What) question is about understanding of the visual scene in the image and the second (Why) question is asking about the rationale. When asking the second (Why) question, the correct answer choice of the first (What) question would also be provided. Every question has four answer choices. Three metrics are calculated, the first two correspond to the two questions respectively, Q2A(Question -> Answer) and QA2R(Question+Correct Answer -> Rationale). The last one is Q2AR which is basically the product of the first two measurements (Q2AR = Q2A x QA2R). There are overall 7 types of VCR questions separated via keywords. 
#### b. Pros ####
The most recognizable dataset for evaluating vision commonsense understanding costing millions of dollars. It is likely still the only highly-semantic VL dataset in Multiple Choice Question(MCQ) format. Lots of its questions are around human intention, emotions, causal and temporal relationships. Because its images are from movies scenes the visual scenes also have diverse varieties.
#### c. Cons #### 
Since its images are from movies, lots of its questions require context from frames before and after. Without enough context, it may be confusing even for human to answer (human oracle accuracy is only around 90%). The questions are heavily biased towards text information since text-only QA model can achieve more than 50% Q2A accuracy. For every question, the authors claim to first conduct adversarial matching across correct answer choices of other questions. Then via rule-based modification, the authors further modify those answer choices to serve as the  distractors. However, the final selected distractors for every question tend to have low qualities comparing with the correct answer choice and thus have space to be further improved. It has strict limited answer distribution thus make it difficult to evaluate generation models.

[Paper Link](https://arxiv.org/pdf/1811.10830.pdf)

![VCR!](VCR.jpg "VCR")
![VCR!](VCR_TYPE.jpg "VCR_TYPE")

### 2. VQA ###
#### a. Description #### 
VQA is a new dataset containing open-ended questions about images. These questions require an understanding of vision, language and commonsense knowledge to answer. It has 265,016 images (mostly from COCO caption dataset and abstract scenes). It also has at least 3 questions (5.4 questions on average) per image, 10 ground truth answers per question. It has two versions VQA V1 and V2. The V2 overall has a more balanced set for types of questions and answer choices. Comparing with VCR, VQA questions tend to include more on visually descriptive questions e.g. spacial relationships, attributes of objects, etc.
It has mainly two types of evaluation metrics, open-ended and multiple-choice. The multiple-choice is differenet from the MCQ in VCR. VCR strictly has four unique answer choices for each question. However in VQA, when answering a question, all the answer choices (including correct answer from other questions) are all provided at once. So the task is to select the correct ones among the large pool. Thus two questions can have the same pool of answer choice candidates.

#### b. Pros #### 
It is the most recognizable Visual Question Answering benchmark. Most of its images are from COCO Captions which are real images. It also includes abstract images which are cartoon images. Its question types are differentiated via starting words of the questions like How many xx?", "What colorxxx?", etc. It has a more diverse set of evaluation metrics, open-ended and multiple-choice which make it possible to evaluate generation models. 

#### c. Cons #### 
The questions are mostly semantically low-level thus it cannot be able to evaluate highly-semantic visual commonsense understanding. Since its question types are separated by starting words of the questions, past works have pointed out that models can learn strong language prior between question types and answer distributions. This bias may be mostly severe when the frequency of answer classes is not balanced, e.g. "What color is xxx?" oftens happen with "White", etc. (refer to paper about VQA-CP, VQA-CE, etc.)

[Paper Link](https://arxiv.org/pdf/1612.00837.pdf)

[Paper Link](https://arxiv.org/pdf/1511.05099.pdf)

[Paper Link](https://arxiv.org/pdf/1505.00468.pdf)


![VCR!](vqa.jpg "VCR")
![VCR!](vqa2.jpg "VCR_TYPE")

### 2. OK-VQA ###
#### a. Description #### 
OK-VQA is a dataset for visual question answering that requires methods which can draw upon outside knowledge to answer questions. It has 14,055 open-ended questions and 5 ground truth answers per question. Its images come from a subset of COCO images. Its questions are categorized into 10 different knowledge categories that each requies.

#### b. Pros #### 
It is manually filtered to ensure all questions require outside knowledge (e.g. from Wikipeida). 

#### c. Cons #### 
Its number of images and questions are very limited comparing with other VL dataset. Also, its average answer length is very short. It follows the same multiple choice evaluation metrics as in VQA but with limited correct answer pool(5 versus 10). It does not provide open-ended evaluation metrics thus it cannot evaluate generation models. 

[Paper Link](https://arxiv.org/pdf/1906.00067.pdf)

![VCR!](okvqa.jpg "VCR")
![VCR!](okvqa2.jpg "VCR_TYPE")
![VCR!](okvqa3.jpg "VCR_TYPE")

### 3. GQA ###
#### a. Description #### 

The authors utilize Visual Genome scene graph structures via question generation engines to create 22M diverse reasoning questions, which all come with functional programs that represent their semantics. Since the questions are generated based on subject, object, attributes and relationships in scene graphs, the semantic focus of the questions are also around these nodes in scene graphs. Based on this generation pipeline from scene grpahs, the authors gain tight control over the answer distribution and present a new tunable smoothing technique to mitigate question biases. Each image comes with a scene graph of objects and relations. Each question comes with a structured representation of its semantics. The images are real images from Visual Genome, COCO and Flickr.

#### b. Pros ####
It claims to overcome the shortcomings of VQA V1 which has a biased distribution of answers and questions. Since VQA V1 is curated basedd on human annotations thus it has limitations in terms of overall balancing of answer distribution and question types due to the high manual cost. On the other hand, question and answers in GQA are mostly generated via scene graph thus it has more power and is convenient to readjust answer and question distribition. Also its generation pipeline allows it to have low manual cost and functional programs that represent semantics behind every question. It inherits from VQA V1 to have both multiple-choice and open-ended evaluation metrics.

#### c. Cons ####
Due to the low-level semantic focus of scene graphs in Visual Genome and limited vocabularies, the questions in GQA are also limited in low-level semantics. The questions focus mostly on attributes, spacial relationships as described in scene graphs. The answer length is also very short due to limited vocabularies in scene graphs.

[Paper Link](https://arxiv.org/pdf/1902.09506.pdf)

![VCR!](gqa.jpg "VCR")
![VCR!](gqa2.jpg "VCR_TYPE")
![VCR!](gqa3.jpg "VCR_TYPE")
![VCR!](gqa4.jpg "VCR_TYPE")

### 4. CLEVER ###
#### a. Description ####
CLEVR: A Diagnostic Dataset for Compositional Language and Elementary Visual Reasoning

The authors claim to present a diagnostic dataset that tests a range of visual reasoning abilities. It contains minimal biases and has detailed annotations describing the kind of reasoning each question requires. Questions in CLEVR test various aspects of visual reasoning including attribute identification, counting, comparison, spatial relationships, and logical operations. Each question in CLEVR is represented both in natural language and as a functional program. The functional program representation allows for precise determination of the reasoning skills required to answer each question.

#### b. Pros ####
Similar to GQA, it has clear semantics graph for describing the reasoning behind the questions; Its questions and answers are also generated thus it has low manual cost.

#### c. Cons #### 
Its images are all rendered non-real-world images and its questions are also around low-level spacial relationship and attributes. The answer length is also very short and thus resultings in limited distribution. 


[Paper Link](https://arxiv.org/pdf/1612.06890.pdf)

![VCR!](clever.jpg "VCR")
![VCR!](clever2.jpg "VCR")


## Other QA ##
### 1. Recipe QA ###
### 2. MovieQA ###
### 3. Visual Spatial Reasoning ###
### 4. IconQA ###
### 5. Visual7W ###

## Generation ##
### 1. VisualCommet ###
#### a. Description ####
Visual COMET: Visual Commonsense Reasoning in Time. 
Reasoning about the Dynamic Context of a Still Image.

It is built on top of validation set of VCR dataset. The authors propose VisualCOMET, the novel framework of visual commonsense reasoning tasks to predict events that might have happened before, events that might happen after, and the intents of the people at present. To support research toward visual commonsense reasoning, we introduce the first large-scale repository of Visual Commonsense Graphs that consists of over 1.4 million textual descriptions of visual commonsense inferences carefully annotated over a diverse set of 60,000 images. Each image is densely annotated with events at present, and the inferences are associated with each pair of event and image. In addition, we provide person-grounding  (i.e., co-reference links) between people appearing in the image and people mentioned in the textual commonsense descriptions.

Dataset Overview
- 60K Images with Place Information
- 139K Events at Present
- 2.3 Events per Image
- 1.4 Million Total Inference Descriptions
- 580K Before Inference Descriptions (4.3 per Event at Present)
- 580K After Inference Descriptions (4.3 per Event at Present)
- 295K Inferences on Intent (2.1 per Event at Present)

Task:  Generate a set of commonsense inferences on 
- events that could've happened before
- events that can happen after
- people's intents at present

#### b. Pros ####
VisualCOMET evolve temporal, intentional information of persons in VCR images. These information helps to mitigate the lack of context information in VCR sample data. The Visual Commonsense Graphs could potentially used for linking between low-level visual clues and high-level information.

#### c. Cons ####
Because the task is to generate a sequence of words thus precide evaluation is difficult. The paper follows the traditional method by using BLEU, CIDEr, METEOR scores. Those traditional scores may not fairly evaluate all potential predictions.

[Paper Link](https://arxiv.org/abs/2004.10796)
![VCR!](visualcommet.jpg "VCR")
![VCR!](visualcommet2.jpg "VCR")

## Language Grounding in Vision #
### 1. Violin #
### 2. Who’s Waldo #

## Other Classification ##
### 1. SNLI-VE ### 
#### a. Description ####
SNLI-VE is built on top of SNLI and Flickr30K. The problem that VE is trying to solve is to reason about the relationship between an image premise P_image and a text hypothesis H_text.

Specifically, given an image as premise, and a natural language sentence as hypothesis, three labels (entailment, neutral and contradiction) are assigned based on the relationship conveyed by the (P_image, H_text)

- entailment holds if there is enough evidence in P_image to conclude that H_text is true.
- contradiction holds if there is enough evidence in P_image to conclude that H_text is false.
- Otherwise, the relationship is neutral, implying the evidence in P_image is insufficient to draw a conclusion about H_text.

Its text is based on the Stanford Natural Language Inference corpus and its images are from Flickr30k.

#### b. Pros ####
It differs from traditional Textual Entailment (TE) tasks like SNLI whereby a premise is defined by an image, rather than a natural language sentence as in TE tasks. It also evolve highly-semantic commonsense of the visual scenes to solve the task.

#### c. Cons ####
It focuses mainly on the overall understanding of the image and may not evaluate finegrained perceptions of the visual scenes e.g. spacial relationships. It also can only evaluate calssification VL models.

[Paper Link](https://arxiv.org/pdf/1811.10582.pdf)
![VCR!](snlive.jpg "VCR")
![VCR!](snlive1.jpg "VCR")
![VCR!](snlive2.jpg "VCR")
![VCR!](snlive3.jpg "VCR")

### 2. e-ViL ###
#### a. Description ####
e-ViL: A Dataset and Benchmark for Natural Language Explanations in Vision-Language Tasks

It is essentially built by merging the explanations from e-SNLI and the image-sentence pairs from SNLI-VE. It also readjust the samples to make answer label distribution more balacned compared with SNLI-VE.

#### b. Pros ####
Similar to SNLI-VE. As it cliams its explanation is not like VCR which often requires external knowledge.

#### c. Cons ####
Similar to SNLI-VE

[Paper Link](https://arxiv.org/pdf/1612.06890.pdf)
![VCR!](evil.jpg "VCR")
![VCR!](evil2.jpg "VCR")
![VCR!](evil3.jpg "VCR")

 
### 3. Visual Genome ###
#### a. Description ####
Visual Genome is a dataset, a knowledge base, an ongoing effort to connect structured image concepts to language.

#### b. Pros ####
#### c. Cons ####
[Paper Link](https://arxiv.org/pdf/1612.06890.pdf)
![VCR!](clever.jpg "VCR")


### 4. VisDial (Visual Dialog) ###


## Composite ##
### 1. VLUE ### 


## Two Recommended References ##
https://github.com/sangminwoo/awesome-vision-and-language#dataset
https://paperswithcode.com/datasets?task=visual-question-answering&page=2 




Visual Storytelling

<!-- ### 1. SNLI-VE ### 
#### a. Description ####
#### b. Pros ####
#### c. Cons ####
[Paper Link](https://arxiv.org/pdf/1612.06890.pdf)
![VCR!](clever.jpg "VCR")
 -->
