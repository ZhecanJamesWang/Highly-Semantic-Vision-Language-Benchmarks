
# Popular QA #
## VCR ## 
    a. Description: Visual Commonsense Reasoning. It is consisted of 290k multiple choice QA problems derived from 110k movie scenes. For every image, there are two types of questions asked. The first (What) question is about understanding of the visual scene in the image and the second (Why) question is asking about the rationale. When asking the second (Why) question, the correct answer choice of the first (What) question would also be provided. Every question has four answer choices. Three metrics are calculated, the first two correspond to the two questions respectively, Q2A(Question -> Answer) and QA2R(Question+Correct Answer -> Rationale). The last one is Q2AR which is basically the product of the first two measurements (Q2AR = Q2A x QA2R). There are overall 7 types of VCR questions
    b. Pros: The most recognizable dataset for evaluating vision commonsense understanding costing millions of dollars. It is likely still the only highly-semantic VL dataset in Multiple Choice Question(MCQ) format. Lots of its questions are around human intention, emotions, causal and temporal relationships. Because its images are from movies scenes the visual scenes also have diverse varieties.
    c. Cons: Since its images are from movies, lots of its questions require context from frames before and after. Without enough context, it may be confusing even for human to answer (human oracle accuracy is only around 90%). The questions are heavily biased towards text information since text-only QA model can achieve more than 50% Q2A accuracy. For every question, the authors claim to first conduct adversarial matching across correct answer choices of other questions. Then via rule-based modification, the authors further modify those answer choices to serve as the  distractors. However, the final selected distractors for every question tend to have low qualities comparing with the correct answer choice and thus have space to be further improved.
    2. VQA: 
        a. Description: VQA is a new dataset containing open-ended questions about images. These questions require an understanding of vision, language and commonsense knowledge to answer. It has 265,016 images (mostly from COCO caption dataset and abstract scenes). It also has at least 3 questions (5.4 questions on average) per image, 10 ground truth answers per question. It has two versions VQA V1 and V2. The V2 overall has a more balanced set for types of questions and answer choices. Comparing with VCR, VQA questions tend to include more on visually descriptive questions e.g. spacial relationships, attributes of objects, etc.



OK-VQA
GQA
CLEVER

Other QA
Recipe QA

Visual Spatial Reasoning
IconQA
Visual7W

Generation
VisualCommet

Language Grounding in Vision
Violin
Who’s Waldo

Other Classification
SNLI-VE
e-ViL
Visual Genome
VisDial (Visual Dialog)

===========
Composite
VLUE


Two Recommended References
https://github.com/sangminwoo/awesome-vision-and-language#dataset
https://paperswithcode.com/datasets?task=visual-question-answering&page=2 




Visual Storytelling

