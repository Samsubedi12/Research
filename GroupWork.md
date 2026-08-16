Below is a **fully revised, comprehensive report draft** based on your original report and the improvements we discussed. I have kept your central ideas—AI/ML threat detection, IDS, malware, phishing, zero-day attacks, XAI, adversarial ML, federated learning, RL, GANs, LLMs and resource constraints—but reorganised them around the actual topic of **AI's impact on cybersecurity**.  
I have also replaced broad/absolute claims such as “AI is 99% accurate” with more academically defensible analysis, and added comparison, research gaps, AI's defensive/offensive dual role, and current 2025 literature.  
## Impact of Artificial Intelligence on Cybersecurity: Applications, Effectiveness, Challenges and Future Directions  
## Abstract  
The rapid expansion of digital infrastructure, cloud computing, Internet of Things (IoT) devices and interconnected services has increased both the scale and complexity of cybersecurity threats. Traditional cybersecurity approaches, particularly signature-based and rule-based detection, remain effective for many known threats but can struggle when attacks are novel, polymorphic, highly automated or capable of changing their observable characteristics. Artificial Intelligence (AI) and Machine Learning (ML) have therefore become increasingly important components of modern cybersecurity because they can process large volumes of security data, identify behavioural patterns, detect anomalies and support automated responses.  
This literature review investigates the impact of AI and ML on cybersecurity, with particular attention to threat detection, intrusion detection, malware and phishing detection, zero-day attack detection, threat intelligence and automated incident response. It examines traditional machine-learning methods, deep learning, reinforcement learning, federated learning, Generative Adversarial Networks (GANs), Transformers and Large Language Models (LLMs). The review also evaluates whether reported improvements in detection performance translate into practical cybersecurity benefits. Existing literature indicates that AI-based intrusion and anomaly detection can provide advantages over purely signature-based approaches, particularly where previously unseen or evolving behaviours must be identified. However, high reported performance on benchmark datasets does not necessarily demonstrate real-world effectiveness, because results can be influenced by dataset composition, class imbalance, feature engineering, experimental design and limited cross-environment validation. (++[ScienceDirect](https://www.sciencedirect.com/science/article/pii/S2665917423001630?utm_source=chatgpt.com)++)  
The review further identifies important challenges including adversarial machine learning, explainability, data quality, computational cost, privacy, model drift and the security risks of LLMs. AI also has a dual-use character: the same technologies that strengthen defensive cybersecurity can support phishing, reconnaissance, vulnerability discovery and other offensive activities. Current research consequently increasingly focuses on trustworthy, explainable, privacy-preserving and adversarially resilient AI. The review concludes that AI should not be regarded as a replacement for conventional cybersecurity but as a complementary capability that can increase the adaptability, scalability and automation of defence when appropriately governed and combined with human expertise.  
**Keywords:** Artificial Intelligence, Machine Learning, Cybersecurity, Intrusion Detection, Deep Learning, Adversarial Machine Learning, Explainable AI, Large Language Models, Threat Detection, Automated Cyber Defence  
  
## 1. Introduction  
## 1.1 Background of Artificial Intelligence and Cybersecurity  
Digital transformation has resulted in organisations becoming increasingly dependent on interconnected information systems, cloud services, mobile devices, IoT infrastructure and online communication. While these technologies improve efficiency and connectivity, they also create a larger attack surface for cybercriminals. Cybersecurity systems must therefore identify and respond to threats that vary in scale, complexity and speed.  
Traditional cybersecurity has historically relied heavily on mechanisms such as signatures, predefined rules, blacklists, firewalls and manually developed detection policies. These approaches remain important because they can provide reliable detection of known and well-characterised threats. However, they are less effective when an attack has not previously been observed or when attackers modify the characteristics of malicious activity to avoid known signatures. Recent literature consequently identifies AI and ML as important technologies for supplementing conventional security mechanisms. (++[ScienceDirect](https://www.sciencedirect.com/science/article/pii/S2665917423001630?utm_source=chatgpt.com)++)  
AI-based cybersecurity systems can analyse large volumes of network traffic, system logs, endpoint activity, URLs, email content and other security telemetry. Machine-learning algorithms can identify relationships within this data and classify activity as benign or malicious. Deep-learning models can learn more complex patterns, while reinforcement-learning approaches can support adaptive decision-making. More recently, Transformers and LLMs have created new possibilities for analysing unstructured security information, supporting threat intelligence and assisting security analysts. Research on LLMs in cybersecurity has expanded rapidly, with recent systematic reviews identifying applications across numerous cybersecurity tasks. (++[DOI](https://doi.org/10.1186/s42400-025-00361-w?utm_source=chatgpt.com)++)  
However, the impact of AI on cybersecurity is not exclusively positive. AI systems themselves can become targets. Attackers may manipulate training data, craft adversarial inputs, exploit weaknesses in models or manipulate LLM prompts. NIST's taxonomy of adversarial machine learning categorises attacks according to the machine-learning lifecycle, attacker objectives and attacker capabilities, demonstrating that securing an AI system requires consideration of threats against the model itself. (++[NIST](https://www.nist.gov/publications/adversarial-machine-learning-taxonomy-and-terminology-attacks-and-mitigations?utm_source=chatgpt.com)++)  
Therefore, the impact of AI on cybersecurity must be assessed from two perspectives:  
1. **AI as a defensive technology**, where it is used to improve threat detection, prevention and response.  
2. **AI as a cybersecurity risk and offensive capability**, where attackers exploit AI or use AI to increase the efficiency and sophistication of attacks.  
This dual perspective forms the foundation of this literature review.  
  
## 1.2 Evolution from Traditional to AI-Driven Cybersecurity  
Traditional cybersecurity approaches generally operate according to predefined knowledge. Signature-based systems, for example, compare observed activity with known malicious patterns. Rule-based systems apply predefined conditions to determine whether activity should be considered suspicious.  
These approaches have several advantages. They are generally easier to understand, relatively efficient and effective against known threats. However, they can have difficulty identifying attacks for which no existing signature or rule is available.  
AI-based cybersecurity changes this approach by enabling systems to learn patterns from data. Instead of relying exclusively on previously defined signatures, anomaly-detection models can establish patterns of normal behaviour and identify deviations. Supervised learning can classify known categories of attacks, while unsupervised and semi-supervised approaches can identify previously unknown patterns.  
The literature therefore suggests that AI should not be understood as a complete replacement for traditional cybersecurity. Rather, the strongest architecture is often a combination of conventional and AI-based approaches. Traditional methods can provide reliable detection for known threats, while AI can provide behavioural analysis and adaptive detection for evolving threats.  
  
## 1.3 Problem Statement  
The central cybersecurity problem is the increasing complexity and adaptability of cyberattacks. Modern attackers can use automation, obfuscation, polymorphism, social engineering and rapidly changing infrastructure to reduce the effectiveness of static detection mechanisms.  
AI-based systems address some of these challenges but introduce new problems. Deep-learning models can be difficult to interpret, creating a “black-box” problem for security analysts. Research on Explainable AI in cybersecurity highlights that understanding why an AI model produces an alert can be particularly important in environments where analysts must validate large numbers of security events. (++[Springer](https://link.springer.com/article/10.1007/s12243-022-00926-7?utm_source=chatgpt.com)++)  
There are also concerns regarding dataset quality and generalisation. A model can achieve excellent performance on a benchmark dataset while performing less effectively when deployed against different network environments or contemporary attacks. This is particularly important in malware detection and intrusion detection research, where datasets can differ considerably in features, attack distributions and collection methods. (++[ScienceDirect](https://www.sciencedirect.com/science/article/pii/S2666827024000227?utm_source=chatgpt.com)++)  
Consequently, the problem is not simply determining whether AI can detect cyberattacks. The more important question is whether AI-based cybersecurity systems can provide **reliable, explainable, scalable, robust and operationally useful protection in realistic environments**.  
  
## 1.4 Aim and Objectives of the Study  
## Aim  
The aim of this literature review is to investigate the impact of Artificial Intelligence and Machine Learning on cybersecurity, with particular emphasis on how AI-based techniques enhance threat detection, cybersecurity monitoring and cyberattack mitigation.  
## Objectives  
The study aims to:  
1. Examine how AI and ML are applied to different cybersecurity problems.  
2. Compare AI-based cybersecurity approaches with traditional cybersecurity mechanisms.  
3. Evaluate the effectiveness of different AI/ML techniques for threat detection and mitigation.  
4. Analyse challenges associated with the deployment of AI-based cybersecurity.  
5. Investigate adversarial attacks and other risks against AI systems.  
6. Examine the role of Explainable AI in improving transparency and analyst trust.  
7. Investigate emerging approaches including federated learning, reinforcement learning, Transformers and LLMs.  
8. Identify research gaps and future directions for secure and trustworthy AI-based cybersecurity.  
  
## 1.5 Research Questions  
## RQ1  
**How are AI and ML techniques being applied to detect and mitigate cybersecurity threats?**  
## RQ2  
**How does the effectiveness of AI-based cybersecurity approaches compare with traditional cybersecurity methods?**  
## RQ3  
**What technical and operational challenges limit the reliability, scalability and deployment of AI-based cybersecurity systems?**  
## RQ4  
**How can Explainable AI, adversarial training, privacy-preserving learning and human oversight improve the trustworthiness of AI-based cybersecurity?**  
  
## 1.6 Significance of the Study  
This study is significant because cybersecurity systems must increasingly operate in environments characterised by large quantities of data and rapidly changing threats. AI provides opportunities to automate security analysis and support security professionals in identifying patterns that may be difficult to recognise manually.  
The review is also significant because it avoids treating AI as an inherently beneficial technology. AI can strengthen defensive capabilities while simultaneously providing new capabilities to attackers. Understanding this balance is important for organisations deciding how and where to deploy AI.  
Finally, the study contributes to understanding the difference between **experimental performance and practical cybersecurity value**. High accuracy on a benchmark dataset is not sufficient evidence that an AI system will be effective in a real operational environment.  
  
## 1.7 Scope of the Literature Review  
The review focuses on AI and ML applications in cybersecurity, including:  
* intrusion and anomaly detection;  
* malware and ransomware detection;  
* phishing detection;  
* zero-day attack detection;  
* threat intelligence;  
* incident response;  
* automated cyber defence;  
* reinforcement learning;  
* federated learning;  
* deep learning;  
* Transformers and LLMs;  
* adversarial machine learning;  
* Explainable AI.  
IoT, edge computing and smart infrastructure are considered as application environments rather than the central focus of the review.  
  
## 2. Literature Review Methodology  
## 2.1 Literature Review Approach  
A structured literature review approach was used to identify and synthesise research concerning AI and ML in cybersecurity. The review prioritised recent research while retaining important foundational concepts necessary for understanding the development of AI-based cybersecurity.  
The evidence base consists primarily of peer-reviewed journal articles, conference publications and authoritative technical publications. Recent literature from 2024–2026 was given particular attention for rapidly developing areas such as LLMs, adversarial ML and federated learning.  
  
## 2.2 Database Selection  
The literature search was designed around major academic and technical sources including:  
* IEEE Xplore;  
* Scopus;  
* Google Scholar;  
* ScienceDirect;  
* SpringerLink;  
* ACM Digital Library;  
* arXiv for emerging AI research;  
* NIST publications for cybersecurity and AI risk-management guidance.  
The use of multiple databases reduces the likelihood that the review will reflect only one research community.  
  
## 2.3 Search Strategy and Keywords  
Search terms were developed around four main concepts: AI, cybersecurity, applications and emerging risks.  
Example search combinations included:  
“Artificial Intelligence” AND “Cybersecurity”  
“Machine Learning” AND “Intrusion Detection”  
“Deep Learning” AND “Malware Detection”  
“Machine Learning” AND “Phishing Detection”  
“AI” AND “Zero-Day Attack Detection”  
“Adversarial Machine Learning” AND “Cybersecurity”  
“Explainable AI” AND “Intrusion Detection”  
“Large Language Models” AND “Cybersecurity”  
“Federated Learning” AND “Intrusion Detection”  
“Reinforcement Learning” AND “Cyber Defence”  
  
## 2.4 Inclusion Criteria  
Studies were included when they:  
* addressed AI, ML, DL, RL, federated learning or LLMs;  
* had a clear cybersecurity application;  
* addressed threat detection, prevention, mitigation, monitoring or response;  
* provided a conceptual, empirical or systematic contribution;  
* were published in English;  
* provided sufficient methodological information for interpretation.  
Recent literature was prioritised for rapidly developing topics.  
  
## 2.5 Exclusion Criteria  
Studies were excluded when they:  
* applied AI to unrelated domains without a cybersecurity connection;  
* provided insufficient information about the methodology;  
* duplicated another publication;  
* were primarily promotional rather than research-oriented;  
* focused exclusively on general AI without cybersecurity relevance.  
  
## 2.6 Study Selection and Screening Process  
The literature selection process followed four broad stages:  
**Identification → Screening → Eligibility → Final Inclusion**  
The initial search produced a broad collection of potentially relevant studies. Titles and abstracts were screened for relevance, followed by full-text assessment. Studies were then grouped according to application area and AI technique.  
A PRISMA-style diagram should be included in the final submitted version to show the actual number of records identified, screened, excluded and retained.  
  
## 2.7 Number and Characteristics of Sources Reviewed  
The revised review synthesises a core set of recent academic and authoritative sources covering AI-based intrusion detection, malware detection, phishing, zero-day attacks, XAI, adversarial ML, federated learning, reinforcement learning and LLM cybersecurity.  
The literature is deliberately distributed across both **technical capability** and **security limitations**, rather than focusing only on studies reporting high detection performance.  
  
## 2.8 Data Extraction  
The following information was extracted from each study:  

| Category          | Information Extracted                            |
| ----------------- | ------------------------------------------------ |
| Publication       | Author and year                                  |
| AI technique      | ML, DL, RL, FL, Transformer, LLM etc.            |
| Application       | IDS, malware, phishing, threat intelligence etc. |
| Dataset           | Dataset or data source                           |
| Evaluation        | Accuracy, precision, recall, F1-score etc.       |
| Main contribution | Key finding                                      |
| Limitation        | Main weakness                                    |
| Deployment        | Centralised, edge, cloud or distributed          |
| Security issue    | Adversarial, privacy, explainability etc.        |
  
## 2.9 Data Analysis and Thematic Synthesis  
The literature was analysed thematically. Six major themes emerged:  
1. AI applications in cybersecurity.  
2. AI/ML model development.  
3. Effectiveness compared with traditional cybersecurity.  
4. Security and operational limitations.  
5. AI's dual defensive and offensive role.  
6. Trustworthy and resilient AI.  
This thematic approach allows studies to be compared according to their contribution rather than simply summarised individually.  
  
## 3. Applications and Impact of AI in Cybersecurity  
## 3.1 AI for Intrusion and Anomaly Detection  
Intrusion Detection Systems (IDS) represent one of the most extensively researched applications of AI in cybersecurity. Traditional IDS approaches often rely on signatures or predefined rules. AI-based IDS can instead analyse network behaviour and classify traffic according to learned patterns.  
A 2023 review of 72 studies found that AI-based IDS research increasingly incorporates machine learning, deep learning and ensemble learning. The review indicates that AI can improve attack-detection performance but also highlights that much research concentrates on overall detection performance rather than the more difficult problem of accurately distinguishing between multiple attack classes. (++[ScienceDirect](https://www.sciencedirect.com/science/article/pii/S2665917423001630?utm_source=chatgpt.com)++)  
Traditional machine-learning models such as Decision Trees, Random Forest, Support Vector Machines and k-Nearest Neighbours remain useful because they can provide comparatively efficient classification. Deep-learning models such as CNNs, LSTMs and GRUs can capture more complex patterns and sequential relationships.  
However, the literature demonstrates an important trade-off. More complex models may improve predictive capability but increase computational requirements and reduce interpretability. Consequently, the most accurate model is not automatically the most suitable model for deployment.  
  
## 3.2 AI for Malware and Ransomware Detection  
Malware represents another major application area for AI. Traditional malware detection often depends on known signatures. This creates difficulties when malware is modified, obfuscated or newly created.  
Deep-learning research has explored static and dynamic malware analysis, classification of executable files, behavioural analysis and representation learning. Recent surveys show that deep learning is increasingly used for malware detection across platforms including Windows, Android, Linux and other environments. (++[ScienceDirect](https://www.sciencedirect.com/science/article/pii/S2666827024000227?utm_source=chatgpt.com)++)  
AI can potentially identify similarities between malicious samples even when their exact signatures differ. This is particularly valuable for identifying malware variants.  
However, malware research demonstrates the importance of cross-dataset validation. A model trained on one malware dataset may learn characteristics specific to that dataset rather than general malicious behaviour. Research therefore identifies generalisation and adversarial robustness as continuing challenges. (++[ScienceDirect](https://www.sciencedirect.com/science/article/pii/S2666827024000227?utm_source=chatgpt.com)++)  
  
## 3.3 AI for Phishing and Social Engineering Detection  
Phishing remains a significant cybersecurity problem because it exploits both technical vulnerabilities and human behaviour. AI-based phishing detection can analyse URLs, domains, webpage characteristics, email text, sender behaviour and other features.  
Recent reviews identify a progression from list-based approaches towards machine learning, deep learning, graph-based approaches, ensemble methods and GAN-based techniques. CNNs and recurrent neural networks have been explored because they can identify complex patterns in phishing-related data. (++[Springer](https://link.springer.com/article/10.1007/s10462-024-11055-z?utm_source=chatgpt.com)++)  
The advantage of ML is that phishing detection can become more adaptive than static blacklists. However, attackers can also modify phishing infrastructure and language rapidly, meaning models require continual evaluation.  
LLMs create another dimension. They can help analyse suspicious messages and summarise contextual information, but they may also make highly convincing social-engineering content easier to produce. Therefore, AI simultaneously strengthens phishing detection and potentially increases phishing capability.  
  
## 3.4 AI for Zero-Day and Emerging Threat Detection  
Zero-day attacks are particularly difficult because defenders may not have a known signature or prior example of the vulnerability being exploited.  
AI can support zero-day detection through anomaly detection, behavioural analysis and models that identify deviations from established patterns. A 2024 systematic review of AI-based zero-day detection identifies AI and ML as promising approaches but also highlights problems involving data availability, algorithmic complexity and real-time deployment. (++[ResearchGate](https://www.researchgate.net/publication/383845725_A_Systematic_Literature_Review_on_AI-Based_Methods_and_Challenges_in_Detecting_Zero-Day_Attacks?utm_source=chatgpt.com)++)  
This leads to an important distinction:  
AI can improve the probability of identifying previously unseen behaviour, but it cannot guarantee detection of every zero-day attack.  
A zero-day attack that closely resembles legitimate activity may remain difficult to distinguish. Consequently, AI should be combined with multiple security controls rather than treated as a standalone solution.  
  
## 3.5 AI for Cyber Threat Intelligence  
Cyber Threat Intelligence (CTI) involves collecting and interpreting information about threats, attackers, vulnerabilities and indicators of compromise.  
AI can process large quantities of security reports, logs, vulnerability information and unstructured text. LLMs are particularly relevant because cybersecurity information is often presented in natural language.  
Recent systematic research into LLMs in cybersecurity has identified applications across numerous cybersecurity tasks and analysed more than 300 works involving multiple LLMs and downstream security scenarios. (++[DOI](https://doi.org/10.1186/s42400-025-00361-w?utm_source=chatgpt.com)++)  
LLMs can therefore support analysts by:  
* summarising threat reports;  
* extracting indicators of compromise;  
* correlating information;  
* explaining technical findings;  
* assisting security documentation;  
* supporting threat-hunting workflows.  
However, LLM outputs must be validated because hallucination and incorrect reasoning can produce unreliable security recommendations.  
  
## 3.6 AI for Security Monitoring and Incident Response  
Security Operations Centres (SOCs) must process large volumes of alerts. AI can assist by correlating events, identifying anomalies, prioritising alerts and generating summaries.  
This can reduce the workload associated with manually examining large quantities of security telemetry. XAI can further help analysts understand why an event was classified as suspicious.  
However, full automation introduces risk. A false positive can trigger unnecessary defensive action, while a false negative can allow an attack to continue. Therefore, AI is particularly valuable as an **analyst-support technology**, rather than an unconditional replacement for human decision-making.  
  
## 3.7 AI for Automated Cyber Defence  
Reinforcement Learning (RL) and Deep Reinforcement Learning (DRL) have attracted interest because they frame cybersecurity as a sequential decision-making problem.  
Instead of simply classifying an event, an RL agent can learn which defensive action is likely to produce a desirable outcome. Potential applications include adaptive intrusion prevention, response selection, network defence and autonomous penetration testing.  
Recent research describes DRL as a promising approach for adaptive threat detection, intrusion prevention and response, while also highlighting challenges including computational complexity, limited training data, adversarial vulnerability and privacy. (++[Sciences Force OJS](https://ojs.sciencesforce.com/index.php/aics/article/view/298?utm_source=chatgpt.com)++)  
Therefore, RL represents a move from:  
**“Is this an attack?”**  
towards:  
**“What should the system do next?”**  
This makes RL particularly relevant to future autonomous cyber-defence systems.  
  
## 4. AI and Machine Learning Approaches in Cybersecurity  
## 4.1 Traditional Machine Learning Approaches  
Traditional ML remains important because many cybersecurity tasks are fundamentally classification problems.  
## Decision Trees and Random Forest  
Decision Trees provide relatively interpretable decision processes. Random Forest combines multiple trees and can provide strong classification performance while reducing some weaknesses of individual trees.  
Their advantages include relatively straightforward training and comparatively lower computational requirements than some deep-learning models.  
## Support Vector Machines  
Support Vector Machines can perform well in high-dimensional classification problems. However, their effectiveness can depend heavily on feature selection and dataset characteristics.  
## Clustering  
Unsupervised clustering can identify groups of similar behaviour without requiring complete labels. This is useful when labelled attack data are limited.  
The overall advantage of traditional ML is that it can provide a balance between performance, computational requirements and interpretability.  
  
## 4.2 Deep Learning Approaches  
Deep learning allows models to learn complex feature representations.  
## Convolutional Neural Networks  
CNNs can identify spatial or structured patterns in transformed cybersecurity data and have been applied to intrusion and malware detection.  
## LSTM and GRU  
LSTM and GRU networks are suitable for sequential data because they can model relationships across time. This makes them relevant for network traffic and behavioural analysis.  
## Hybrid Models  
Hybrid architectures such as CNN-GRU combine feature extraction with temporal modelling. Such models may produce strong experimental results, but their practical usefulness depends on inference cost, dataset quality and generalisation.  
The literature therefore does not justify simply selecting the model with the highest accuracy. Model selection should consider:  
* detection performance;  
* computational cost;  
* explainability;  
* robustness;  
* scalability;  
* latency;  
* deployment environment.  
  
## 4.3 Reinforcement Learning and Deep Reinforcement Learning  
RL differs from conventional supervised learning because the model learns through interaction with an environment.  
In cybersecurity, an RL agent can potentially learn:  
* when to block traffic;  
* when to isolate a device;  
* which response strategy to select;  
* how to prioritise threats;  
* how to adapt to changing attacker behaviour.  
However, safe training is difficult. Poorly designed reward functions may encourage undesirable behaviour. Furthermore, autonomous defensive actions can have significant operational consequences.  
  
## 4.4 Federated Learning for Privacy-Preserving Cybersecurity  
Federated Learning (FL) enables multiple organisations or devices to train a shared model without directly transferring their raw training data to a central location.  
This is particularly relevant to cybersecurity because security data can contain sensitive information.  
Recent surveys identify FL as a promising approach for distributed IDS because it can support collaborative learning while keeping data at local sites. However, FL introduces communication costs, heterogeneous data, non-IID data and security risks involving malicious clients and model updates. (++[Torrens University Australia](https://research.torrens.edu.au/en/publications/survey-on-federated-learning-for-intrusion-detection-system-conce/?utm_source=chatgpt.com)++)  
Therefore:  
**Federated learning improves data-sharing privacy but does not automatically make machine learning secure.**  
The FL process itself requires protection.  
  
## 4.5 Transformers and Large Language Models  
Transformers have significantly influenced AI research because of their ability to model long-range relationships in sequential and textual data.  
In cybersecurity, Transformers can be applied to:  
* network traffic;  
* log analysis;  
* malware representations;  
* threat reports;  
* vulnerability information;  
* security questions;  
* incident-response documentation.  
LLMs extend these capabilities into natural-language interaction.  
Recent reviews identify applications of LLMs across threat detection, vulnerability assessment, incident response and threat intelligence. (++[DOI](https://doi.org/10.3390/ai6090216?utm_source=chatgpt.com)++)  
Nevertheless, LLMs introduce security concerns such as prompt injection, data poisoning, information leakage, jailbreaking and unreliable outputs. (++[ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S2214212625003217?utm_source=chatgpt.com)++)  
  
## 4.6 Generative AI and GANs  
GANs consist of a generator and discriminator that compete during training. In cybersecurity research, GANs have been investigated for generating synthetic attack samples and addressing class imbalance.  
This can be useful because cybersecurity datasets often contain significantly more benign samples than examples of rare attack classes.  
A 2023 survey of GANs in cybersecurity intrusion detection identifies their growing use for addressing imbalanced attack datasets. (++[ResearchGate](https://www.researchgate.net/publication/372404301_A_Comprehensive_Survey_of_Generative_Adversarial_Networks_GANs_in_Cybersecurity_Intrusion_Detection?utm_source=chatgpt.com)++)  
However, synthetic data must be carefully validated. Artificially generated attack samples may not accurately represent real attacker behaviour.  
  
## 4.7 Comparative Analysis of AI/ML Approaches  

| Approach | Main Cybersecurity Use | Major Strength | Major Limitation |
| ------------------ | ---------------------- | -------------------------------------- | --------------------------------- |
| Decision Tree | Classification/IDS | Interpretable | Can overfit |
| Random Forest | IDS/Malware | Strong general-purpose classifier | Less adaptive without retraining |
| SVM | Classification | Effective in high-dimensional data | Sensitive to feature/data choices |
| CNN | IDS/Malware | Learns complex patterns | Computational cost |
| LSTM/GRU | Sequential detection | Captures temporal behaviour | Training/inference cost |
| Hybrid CNN-GRU | IDS | Combines feature and temporal learning | Greater complexity |
| RL/DRL | Adaptive defence | Supports sequential decisions | Difficult training and validation |
| Federated Learning | Distributed IDS | Data remains local | Communication/security challenges |
| Transformer | Logs/traffic/CTI | Long-range relationships | Resource intensive |
| LLM | CTI/analyst support | Natural-language reasoning | Hallucination and security risks |
| GAN | Data augmentation | Addresses class imbalance | Synthetic data may lack realism |
  
## 5. Effectiveness of AI Compared with Traditional Cybersecurity  
## 5.1 Traditional Signature-Based and Rule-Based Approaches  
Traditional approaches remain valuable because they provide deterministic responses to known threats.  
For example, if a malware sample has an established signature, signature-based detection can be highly efficient.  
The limitation appears when the threat has no known signature or has been modified.  
Therefore, it is more accurate to describe traditional cybersecurity as **limited against some forms of novel and adaptive attacks**, rather than obsolete.  
  
## 5.2 Detection of Known and Unknown Threats  
AI's major advantage is its ability to learn behavioural patterns.  
Traditional methods:  
Known signature → match → alert.  
AI-based anomaly detection:  
Learn normal/attack behaviour → identify deviation → generate alert.  
This makes AI particularly relevant for zero-day and previously unseen attacks. However, anomaly detection can also produce false positives when legitimate behaviour differs significantly from the training distribution.  
The literature therefore suggests that AI can improve unknown-threat detection but cannot eliminate the fundamental uncertainty associated with novel attacks. (++[ResearchGate](https://www.researchgate.net/publication/383845725_A_Systematic_Literature_Review_on_AI-Based_Methods_and_Challenges_in_Detecting_Zero-Day_Attacks?utm_source=chatgpt.com)++)  
  
## 5.3 Detection Accuracy and Performance  
Many experimental studies report high detection accuracy for AI-based cybersecurity models. However, accuracy must be interpreted carefully.  
For example, a dataset with a very large proportion of benign traffic could allow a model to achieve high overall accuracy while performing poorly on rare attack classes.  
Therefore, appropriate evaluation should consider:  
* precision;  
* recall;  
* F1-score;  
* false-positive rate;  
* false-negative rate;  
* detection latency;  
* resource consumption.  
The literature review of AI-based IDS research specifically identifies a strong emphasis on detection performance while noting the continuing challenge of multi-class attack classification. (++[ScienceDirect](https://www.sciencedirect.com/science/article/pii/S2665917423001630?utm_source=chatgpt.com)++)  
  
## 5.4 False Positives and False Negatives  
A cybersecurity system must balance two major errors.  
## False positive  
Legitimate activity is classified as malicious.  
## False negative  
Malicious activity is classified as legitimate.  
Both can be costly.  
High false-positive rates can create alert fatigue and overwhelm analysts. XAI research highlights the importance of helping security operators understand and validate AI-generated alerts. (++[Springer](https://link.springer.com/article/10.1007/s12243-022-00926-7?utm_source=chatgpt.com)++)  
False negatives can be even more serious because an attack may continue undetected.  
Consequently, an AI model should not be judged by accuracy alone.  
  
## 5.5 Scalability and Real-Time Detection  
AI can process large volumes of telemetry more rapidly than manual analysis. However, scalability depends on model complexity.  
A small Random Forest model may be suitable for an edge device, while a large Transformer may require significant computational infrastructure.  
Federated learning provides one possible solution for distributed environments because it enables collaborative learning without requiring all raw data to be centralised. Nevertheless, FL introduces communication and coordination overhead. (++[Torrens University Australia](https://research.torrens.edu.au/en/publications/survey-on-federated-learning-for-intrusion-detection-system-conce/?utm_source=chatgpt.com)++)  
  
## 5.6 Adaptability to Evolving Cyber Threats  
One of AI's strongest theoretical advantages is adaptability.  
Attackers continually modify:  
* malware;  
* phishing content;  
* infrastructure;  
* command-and-control behaviour;  
* attack sequences.  
A static rule may become ineffective when the attack changes. ML systems can potentially be retrained or updated to reflect new patterns.  
However, this creates another problem: **model drift**.  
A model trained on historical attack behaviour may gradually become less effective as attacker behaviour changes.  
Therefore:  
AI creates the possibility of adaptive cybersecurity, but maintaining adaptation requires continuous monitoring, validation and retraining.  
  
## 5.7 Computational and Resource Requirements  
Deep learning and LLMs can require substantial computational resources.  
This creates a deployment problem:  
The models capable of sophisticated analysis may not always be suitable for resource-constrained environments.  
This is particularly relevant to IoT and edge devices.  
Federated learning and lightweight models provide possible solutions, but the literature continues to identify computational, communication and deployment challenges. (++[ScienceDirect](https://www.sciencedirect.com/science/article/pii/S1389128624008557?utm_source=chatgpt.com)++)  
  
## 5.8 Overall Comparison  

| Factor | Traditional Cybersecurity | AI-Based Cybersecurity |
| ------------------------- | ------------------------- | ---------------------------- |
| Known threats | Strong | Strong |
| Unknown threats | Limited | Potentially stronger |
| Adaptability | Relatively low | Potentially high |
| Automation | Moderate | High |
| Explainability | Usually high | Often lower |
| Computational cost | Usually lower | Can be high |
| Data requirements | Lower | Often significant |
| False positives | Possible | Possible |
| Zero-day detection | Limited | Promising but not guaranteed |
| Human oversight | High | Still necessary |
| Adversarial vulnerability | Lower model-specific risk | Significant |
| Scalability | Depends on architecture | Potentially high |
  
The comparison demonstrates that AI does not simply make every aspect of cybersecurity better. Instead, AI changes the trade-offs between adaptability, automation, accuracy, interpretability, computational requirements and security risk.  
  
## 6. Challenges and Risks of AI-Driven Cybersecurity  
## 6.1 Explainability and the Black-Box Problem  
Deep-learning systems may produce highly complex decision boundaries that are difficult for humans to understand.  
In cybersecurity, this can be problematic because analysts need to determine whether an alert is genuine and what action should follow.  
XAI methods such as SHAP and LIME can provide explanations of model decisions. SHAP can estimate the contribution of individual features, while LIME provides local approximations of particular predictions. (++[PubMed Central (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC11877648/?utm_source=chatgpt.com)++)  
However, XAI itself introduces computational and security considerations.  
Therefore, the objective should not simply be:  
“Make the model explainable.”  
It should be:  
“Provide explanations that are accurate, understandable, useful and timely for the security analyst.”  
  
## 6.2 Adversarial Machine Learning  
AI systems can be attacked.  
NIST categorises adversarial ML according to attack lifecycle, attacker goals and capabilities. Relevant categories include attacks that manipulate inputs, training data or model behaviour. (++[NIST](https://www.nist.gov/publications/adversarial-machine-learning-taxonomy-and-terminology-attacks-and-mitigations?utm_source=chatgpt.com)++)  
Examples include:  
* evasion attacks;  
* poisoning attacks;  
* backdoor attacks;  
* model extraction;  
* model manipulation.  
This creates a fundamental problem:  
The cybersecurity system becomes another asset that attackers may target.  
AI-based cybersecurity therefore requires security controls for the AI model itself.  
  
## 6.3 Data Quality, Bias and Dataset Limitations  
Machine learning depends on data.  
Poor-quality training data can produce:  
* biased models;  
* poor generalisation;  
* excessive false positives;  
* poor detection of rare attacks.  
Cybersecurity datasets are particularly difficult because real attacks may be rare, sensitive or difficult to label.  
This explains why benchmark results must be interpreted cautiously.  
Research on malware detection specifically identifies limitations in benchmark availability and generalisation across datasets. (++[ScienceDirect](https://www.sciencedirect.com/science/article/pii/S2666827024000227?utm_source=chatgpt.com)++)  
  
## 6.4 Model Drift and Changing Attack Patterns  
Cyber threats evolve continuously.  
Consequently, an AI system trained today may not perform equally well in the future.  
Continuous retraining can address this problem, but retraining introduces:  
* computational cost;  
* data-management requirements;  
* potential poisoning risks;  
* validation requirements.  
Organisations therefore need mechanisms for monitoring model performance over time.  
  
## 6.5 Computational and Infrastructure Requirements  
Large neural networks and LLMs can require substantial hardware resources.  
This can create barriers for:  
* small organisations;  
* IoT devices;  
* edge environments;  
* low-latency applications.  
A practical AI cybersecurity architecture may therefore need multiple model sizes operating at different layers.  
For example:  
**Edge:** lightweight anomaly detection  
↓  
**Network:** ML-based traffic analysis  
↓  
**Cloud/SOC:** deep learning and LLM-based analysis  
This layered architecture can combine speed and sophistication.  
  
## 6.6 Privacy and Data Protection  
Cybersecurity data can contain:  
* user information;  
* network addresses;  
* communications;  
* behavioural patterns;  
* system configurations;  
* sensitive organisational information.  
Centralising such information for AI training can increase privacy risks.  
Federated learning addresses part of this problem by allowing local training while sharing model updates rather than raw data. However, FL itself remains vulnerable to security and privacy challenges. (++[Torrens University Australia](https://research.torrens.edu.au/en/publications/survey-on-federated-learning-for-intrusion-detection-system-conce/?utm_source=chatgpt.com)++)  
  
## 6.7 False Positives, False Negatives and Reliability  
AI-generated security alerts must be sufficiently reliable for operational use.  
A system that produces thousands of poorly prioritised alerts may increase rather than reduce the workload of analysts.  
Therefore, future AI cybersecurity systems should optimise not only detection accuracy but also:  
* alert prioritisation;  
* confidence estimation;  
* explanation quality;  
* response recommendations;  
* analyst workload.  
  
## 6.8 Security Risks Associated with LLMs  
LLMs introduce a new set of cybersecurity concerns.  
Recent literature identifies threats including:  
* prompt manipulation;  
* prompt injection;  
* data poisoning;  
* privacy leakage;  
* jailbreaking;  
* malicious use;  
* unreliable outputs;  
* risks associated with autonomous agents.  
A 2025 systematic review of LLM security identifies inference-time attacks, training-time attacks, malicious use and risks associated with autonomous LLM agents. (++[ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S2214212625003217?utm_source=chatgpt.com)++)  
Therefore, an LLM used for cybersecurity should not automatically be trusted to execute security actions without appropriate controls.  
  
## 6.9 Ethical and Governance Challenges  
AI cybersecurity systems can influence decisions that affect individuals and organisations.  
Potential issues include:  
* privacy;  
* bias;  
* accountability;  
* transparency;  
* inappropriate automation;  
* misuse;  
* unclear responsibility when an AI-generated decision causes harm.  
NIST's AI Risk Management Framework provides a structured approach for organisations to manage AI risks and promote trustworthy AI. Its functions include **Govern, Map, Measure and Manage**. (++[NIST](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-ai-rmf-10?utm_source=chatgpt.com)++)  
These principles are particularly relevant when AI is deployed in high-impact cybersecurity environments.  
  
## 7. AI as Both a Defensive and Offensive Cybersecurity Capability  
## 7.1 AI for Defensive Cybersecurity  
AI can support defenders by:  
* detecting anomalies;  
* classifying malware;  
* identifying phishing;  
* prioritising alerts;  
* analysing threat intelligence;  
* supporting incident response;  
* identifying suspicious behaviour;  
* automating repetitive SOC tasks.  
This represents the positive security impact of AI.  
  
## 7.2 AI-Enabled Phishing and Social Engineering  
The same generative capabilities used by defenders can help attackers produce convincing text.  
LLMs can potentially increase the scale and personalisation of social-engineering campaigns.  
This means AI may lower some barriers to creating persuasive malicious communications.  
Therefore, AI-driven phishing detection must evolve alongside AI-assisted phishing.  
  
## 7.3 AI-Assisted Malware and Attack Generation  
Generative AI can potentially assist attackers in modifying or generating malicious content.  
However, it is important not to assume that AI automatically produces sophisticated malware. Real-world attack capability depends on operational infrastructure, access, knowledge and constraints beyond the model itself.  
The more defensible conclusion is that AI can **increase automation and reduce effort in parts of the attack lifecycle**, creating additional pressure on defenders.  
  
## 7.4 AI-Assisted Reconnaissance and Vulnerability Discovery  
AI can analyse large quantities of technical information and assist with identifying relationships between systems, technologies and vulnerabilities.  
This creates opportunities for defensive vulnerability management but also introduces offensive applications.  
Research on autonomous penetration testing increasingly investigates reinforcement learning for attack-path planning and automated security assessment. (++[ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0957417425038345?utm_source=chatgpt.com)++)  
  
## 7.5 Adversarial Attacks Against AI-Based Security Systems  
Attackers may specifically target the AI system rather than the protected network.  
The MITRE ATLAS knowledge base documents adversarial tactics and techniques targeting AI-enabled systems and includes areas such as reconnaissance, model access, defense evasion, credential access, discovery and other attack stages. (++[MITRE ATLAS](https://atlas.mitre.org/?utm_source=chatgpt.com)++)  
This demonstrates that securing AI requires treating the AI system as part of the attack surface.  
  
## 7.6 The Emerging AI Cybersecurity Arms Race  
The relationship between AI and cybersecurity can therefore be viewed as a continuous cycle:  
**Attackers use AI**  
↓  
**Defenders develop AI-based detection**  
↓  
**Attackers adapt**  
↓  
**Defenders retrain and improve models**  
↓  
**Attackers target the AI systems themselves**  
This creates an emerging AI cybersecurity arms race.  
The implication is that static AI solutions are unlikely to remain effective indefinitely.  
  
## 8. Explainable, Trustworthy and Resilient AI for Cybersecurity  
## 8.1 Explainable Artificial Intelligence  
XAI aims to make AI decisions more understandable.  
In cybersecurity, this can help analysts determine:  
* why an alert was generated;  
* which features influenced the prediction;  
* whether the decision appears reasonable;  
* what evidence supports the classification.  
Research indicates that XAI can improve transparency and analyst trust, although explanation quality and computational cost remain important challenges. (++[Springer](https://link.springer.com/article/10.1007/s12243-022-00926-7?utm_source=chatgpt.com)++)  
  
## 8.2 SHAP, LIME and Other Explainability Techniques  
## SHAP  
SHAP provides feature-attribution values indicating how individual features contribute to a prediction.  
## LIME  
LIME creates local explanations for individual predictions.  
Both can help security analysts understand complex AI models, but neither completely solves the black-box problem.  
The choice of explanation technique should therefore depend on:  
* model type;  
* required explanation speed;  
* analyst needs;  
* deployment environment;  
* privacy requirements.  
  
## 8.3 Adversarial Training and Robust AI  
Adversarial training involves exposing models to carefully designed difficult examples during training.  
The objective is to make models less vulnerable to manipulation.  
However, adversarial robustness is not a single property. A model may become more robust against one attack type while remaining vulnerable to another.  
NIST's adversarial ML taxonomy emphasises the need to consider different attacker goals and capabilities rather than treating adversarial attacks as one uniform category. (++[NIST](https://www.nist.gov/publications/adversarial-machine-learning-taxonomy-and-terminology-attacks-and-mitigations?utm_source=chatgpt.com)++)  
  
## 8.4 Human-in-the-Loop Cybersecurity  
Human oversight remains important.  
A practical architecture should allow AI to:  
1. detect;  
2. explain;  
3. prioritise;  
4. recommend.  
The human analyst can then:  
5. validate;  
6. approve;  
7. modify;  
8. execute high-impact responses.  
This is particularly important where automated actions could disrupt legitimate services.  
  
## 8.5 Zero Trust and AI-Driven Security  
Zero Trust is based on continuous verification rather than assuming that a user or device is trustworthy simply because it is inside a network.  
AI can support Zero Trust by analysing behavioural signals and identifying deviations.  
However, AI should support Zero Trust decisions rather than become the sole basis for them.  
  
## 8.6 Privacy-Preserving AI  
Federated learning provides one important approach.  
Instead of:  
Data → central server → training  
the architecture becomes:  
Local data → local training → model update → aggregation → improved shared model  
This can reduce the need to centralise sensitive data.  
However, model updates themselves may require protection, and malicious participants can potentially compromise the federated process. (++[Torrens University Australia](https://research.torrens.edu.au/en/publications/survey-on-federated-learning-for-intrusion-detection-system-conce/?utm_source=chatgpt.com)++)  
  
## 8.7 Lightweight AI for Edge and IoT Environments  
The growing number of IoT and edge devices creates a need for lightweight models.  
Potential techniques include:  
* feature selection;  
* dimensionality reduction;  
* model compression;  
* knowledge distillation;  
* lightweight neural networks;  
* edge-cloud collaboration.  
The objective is to maintain acceptable detection performance without requiring the resources of large centralised models.  
  
## 8.8 Towards Trustworthy and Autonomous Cyber Defence  
The long-term direction of AI cybersecurity is likely to involve increasingly autonomous systems.  
However, autonomy should be accompanied by:  
* explainability;  
* monitoring;  
* robust evaluation;  
* human oversight;  
* secure model updates;  
* access controls;  
* auditability.  
NIST's AI RMF provides a useful high-level framework for integrating trustworthiness considerations throughout AI development and deployment. (++[NIST](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-ai-rmf-10?utm_source=chatgpt.com)++)  
  
## 9. Comparative Analysis, Research Gaps and Future Directions  
## 9.1 Synthesis of Findings Across the Literature  
The literature consistently demonstrates that AI has significant potential in cybersecurity, particularly in environments where large amounts of data must be processed quickly.  
However, three major conclusions emerge.  
## Finding 1: AI improves the adaptability of cybersecurity  
AI can identify patterns that are difficult to capture using fixed rules.  
## Finding 2: Performance results require contextual interpretation  
Very high accuracy does not necessarily imply real-world effectiveness.  
## Finding 3: AI introduces new risks  
AI systems can themselves be attacked, manipulated or misused.  
Therefore, the impact of AI is best described as **transformative but conditional**.  
  
## 9.2 Comparison of AI/ML Models and Applications  

| AI Approach | Primary Application | Advantages | Key Challenges |
| ------------- | --------------------- | ----------------------------------------- | --------------------------------- |
| Random Forest | IDS/Malware | Efficient and comparatively interpretable | Limited adaptability |
| SVM | Threat classification | Strong classification capability | Feature sensitivity |
| CNN | IDS/Malware | Learns complex representations | Computational requirements |
| LSTM/GRU | Behaviour analysis | Temporal modelling | Training complexity |
| CNN-GRU | IDS | Combines spatial/temporal patterns | Greater model complexity |
| DRL | Automated defence | Adaptive decision-making | Difficult training |
| FL | Distributed IDS | Privacy-preserving collaboration | Communication and poisoning risks |
| Transformer | Logs/traffic | Long-range dependencies | Resource requirements |
| LLM | CTI/SOC support | Natural-language reasoning | Hallucination/security risks |
| GAN | Data augmentation | Addresses imbalance | Synthetic-data quality |
  
## 9.3 Key Findings and Areas of Agreement  
Across the literature, several broad areas of agreement emerge:  
1. AI can enhance cybersecurity threat detection.  
2. AI is particularly valuable for large-scale data analysis.  
3. Deep learning can identify complex patterns.  
4. AI can support detection of evolving and potentially unknown threats.  
5. Explainability remains a major challenge.  
6. Dataset quality significantly affects results.  
7. AI systems themselves require security controls.  
8. Human oversight remains important.  
9. Federated learning provides opportunities for privacy-preserving collaborative detection.  
10. LLMs create both defensive opportunities and new security risks.  
  
## 9.4 Contradictions and Inconsistencies in the Literature  
One of the most important contradictions concerns model performance.  
Some experimental studies report extremely high detection accuracy, while broader reviews identify difficulties with generalisation and real-world deployment. (++[ScienceDirect](https://www.sciencedirect.com/science/article/pii/S2665917423001630?utm_source=chatgpt.com)++)  
This difference may be explained by:  
* different datasets;  
* different train/test splits;  
* class imbalance;  
* synthetic traffic;  
* different evaluation metrics;  
* feature-engineering choices;  
* different threat models.  
Consequently, comparing two studies solely according to reported accuracy can be misleading.  
A more meaningful comparison should consider:  
**Accuracy + recall + false-positive rate + dataset realism + computational cost + generalisation + adversarial robustness.**  
  
## 9.5 Limitations of Existing Research  
The reviewed literature identifies several recurring limitations.  
## Dataset dependence  
Many systems are evaluated using established benchmark datasets rather than continuously collected operational data.  
## Limited cross-environment validation  
A model may perform well in one network environment but not another.  
## Limited real-world deployment  
Many proposed systems remain experimental.  
## Explainability-performance trade-off  
Increasing interpretability can introduce computational overhead.  
## Adversarial robustness  
Models can remain vulnerable to manipulation.  
## Resource requirements  
Large models may not be appropriate for edge devices.  
## Rapid technological change  
LLMs and generative AI are developing faster than traditional cybersecurity evaluation methodologies.  
  
## 9.6 Identified Research Gaps  
## Gap 1: Real-world evaluation  
Future studies should evaluate models across multiple organisations, networks and datasets.  
## Gap 2: Cross-dataset generalisation  
Researchers should test whether models trained on one dataset maintain performance on another.  
## Gap 3: Standardised evaluation  
There is a need for consistent evaluation metrics and realistic threat scenarios.  
## Gap 4: Explainability in real-time systems  
XAI techniques need to operate quickly enough for real-world security operations.  
## Gap 5: Robustness against adversarial attacks  
AI cybersecurity models require stronger evaluation against adaptive attackers.  
## Gap 6: Secure LLM deployment  
Research must address prompt injection, data leakage, hallucination and autonomous-agent risks.  
## Gap 7: Lightweight AI  
More work is needed on efficient AI for edge and IoT environments.  
## Gap 8: Human-AI collaboration  
Research should evaluate whether AI actually improves analyst decision-making rather than simply measuring model accuracy.  
  
## 9.7 Future Research Directions  
## 9.7.1 Real-World and Cross-Dataset Evaluation  
Future research should move beyond single benchmark datasets and evaluate models across multiple environments.  
## 9.7.2 Adversarially Robust AI  
AI systems should be evaluated against multiple adversarial attack categories throughout their lifecycle.  
## 9.7.3 Explainable and Human-Centred AI  
Future XAI systems should prioritise explanations that are actionable for analysts rather than simply technically interpretable.  
## 9.7.4 Secure LLMs  
Research should focus on:  
* prompt injection;  
* hallucination reduction;  
* data protection;  
* secure tool use;  
* model monitoring;  
* agent security.  
Recent research demonstrates that LLM cybersecurity is now a substantial research area rather than a niche application. (++[DOI](https://doi.org/10.1186/s42400-025-00361-w?utm_source=chatgpt.com)++)  
## 9.7.5 Lightweight AI for Edge and IoT Security  
Future systems should balance:  
**accuracy + latency + memory + energy consumption + robustness.**  
## 9.7.6 Autonomous and Adaptive Cyber Defence  
RL, LLM agents and automated response systems may eventually support increasingly autonomous defence.  
However, high-impact actions should remain subject to appropriate safeguards and human oversight.  
  
## 10. Conclusion and Recommendations  
## 10.1 Summary of Key Findings  
This literature review investigated the impact of Artificial Intelligence and Machine Learning on cybersecurity.  
The findings demonstrate that AI is increasingly being applied to:  
* intrusion detection;  
* anomaly detection;  
* malware detection;  
* phishing detection;  
* zero-day detection;  
* threat intelligence;  
* security monitoring;  
* incident response;  
* automated defence.  
AI provides particular value because it can analyse large quantities of data and identify complex behavioural patterns. Deep learning expands these capabilities by learning representations from complex data, while reinforcement learning provides opportunities for adaptive decision-making.  
However, the literature does not support the conclusion that AI universally replaces traditional cybersecurity.  
Traditional methods remain valuable for known threats, while AI provides complementary capabilities for behavioural analysis and emerging threats.  
  
## 10.2 Answer to the Research Questions  
## RQ1: How are AI and ML techniques being applied to detect and mitigate cybersecurity threats?  
AI and ML are applied across multiple cybersecurity domains, including IDS, malware detection, phishing detection, anomaly detection, threat intelligence and incident response. Emerging technologies such as LLMs extend these applications into natural-language analysis and security-assistant functions.  
## RQ2: How does AI compare with traditional cybersecurity?  
AI can provide greater adaptability and automation, particularly for behavioural and anomaly-based detection. However, traditional signature and rule-based methods remain effective for known threats. The strongest approach is therefore likely to combine conventional controls with AI-based analysis.  
## RQ3: What challenges limit AI cybersecurity?  
Major challenges include dataset quality, generalisation, false positives, computational requirements, model drift, explainability, privacy and adversarial attacks.  
## RQ4: How can AI cybersecurity become more trustworthy?  
Trustworthiness can be improved through XAI, adversarial training, privacy-preserving learning, secure model development, human oversight, continuous evaluation and risk-management frameworks.  
  
## 10.3 Overall Impact of AI on Cybersecurity  
The overall impact of AI on cybersecurity can be characterised as **transformative rather than universally substitutive**.  
AI changes cybersecurity from a predominantly rule-driven model towards a more:  
* adaptive;  
* data-driven;  
* automated;  
* predictive;  
* behaviour-based  
approach.  
However, this transformation introduces new dependencies and risks.  
The most important conclusion is therefore:  
**AI should be treated as a powerful cybersecurity capability rather than a complete cybersecurity solution.**  
Its effectiveness depends on the quality of data, model robustness, deployment environment, explainability, human oversight and integration with existing security controls.  
  
## 10.4 Recommendations for Cybersecurity Practitioners  
Organisations adopting AI-based cybersecurity should:  
1. Use AI alongside rather than instead of established security controls.  
2. Evaluate models using precision, recall, F1-score and false-positive/negative rates rather than accuracy alone.  
3. Test models across multiple datasets and realistic environments.  
4. Continuously monitor model performance for drift.  
5. Implement XAI where analysts need to understand automated decisions.  
6. Conduct adversarial robustness testing.  
7. Protect training data and model-update pipelines.  
8. Use federated or privacy-preserving approaches where appropriate.  
9. Maintain human oversight over high-impact automated responses.  
10. Apply formal AI risk-management processes.  
  
## 10.5 Recommendations for Organisations  
Organisations should establish governance procedures covering:  
* data quality;  
* model validation;  
* access control;  
* monitoring;  
* auditability;  
* incident response;  
* privacy;  
* AI security;  
* human accountability.  
NIST's AI Risk Management Framework provides a useful structure for managing AI risks through the functions of Govern, Map, Measure and Manage. (++[NIST](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-ai-rmf-10?utm_source=chatgpt.com)++)  
  
## 10.6 Recommendations for Future Research  
Future research should prioritise:  
1. **Real-world evaluation** rather than relying exclusively on benchmark datasets.  
2. **Cross-dataset generalisation** to determine whether models remain effective in unfamiliar environments.  
3. **Adversarially resilient AI** capable of resisting manipulation.  
4. **Explainable AI** that produces actionable explanations in real time.  
5. **Secure LLMs and AI agents** capable of operating safely in cybersecurity environments.  
6. **Lightweight AI** for edge and IoT environments.  
7. **Human-AI collaboration** that evaluates improvements in analyst decision-making.  
8. **Standardised evaluation frameworks** for comparing AI cybersecurity systems fairly.  
  
## References  
1. Salem, A. H., Azzam, S. M., Emam, O. E., & Abohany, A. A. (2024). *Advancing cybersecurity: A comprehensive review of AI-driven detection techniques*. Journal of Big Data, 11, 105. (++[Springer](https://link.springer.com/article/10.1186/s40537-024-00957-y?utm_source=chatgpt.com)++)  
2. *A comprehensive review of AI based intrusion detection system*. (2023). Measurement: Sensors, 28, 100827. (++[ScienceDirect](https://www.sciencedirect.com/science/article/pii/S2665917423001630?utm_source=chatgpt.com)++)  
3. Kavya, S., & Sumathi, D. (2025). *Staying ahead of phishers: A review of recent advances and emerging methodologies in phishing detection*. Artificial Intelligence Review, 58, 50. (++[Springer](https://link.springer.com/article/10.1007/s10462-024-11055-z?utm_source=chatgpt.com)++)  
4. *A survey of malware detection using deep learning*. (2024). Machine Learning with Applications, 16, 100546. (++[ScienceDirect](https://www.sciencedirect.com/science/article/pii/S2666827024000227?utm_source=chatgpt.com)++)  
5. Por, L. Y., Dai, Z., Leem, S. J., Chen, Y., et al. (2024). *A systematic literature review on AI-based methods and challenges in detecting zero-day attacks*. IEEE Access, 12, 144150–144163. (++[ResearchGate](https://www.researchgate.net/publication/383845725_A_Systematic_Literature_Review_on_AI-Based_Methods_and_Challenges_in_Detecting_Zero-Day_Attacks?utm_source=chatgpt.com)++)  
6. Abouhawwash, M. (2024). *Innovations in Cyber Defense with Deep Reinforcement Learning: A Concise and Contemporary Review*. Artificial Intelligence in Cybersecurity, 1, 44–51. (++[Sciences Force OJS](https://ojs.sciencesforce.com/index.php/aics/article/view/298?utm_source=chatgpt.com)++)  
7. Khraisat, A., Alazab, A., Singh, S., Jan, T., & Gomez, A. (2024). *Survey on Federated Learning for Intrusion Detection System: Concept, Architectures, Aggregation Strategies, Challenges, and Future Directions*. ACM Computing Surveys, 57(1), Article 7. (++[Torrens University Australia](https://research.torrens.edu.au/en/publications/survey-on-federated-learning-for-intrusion-detection-system-conce/?utm_source=chatgpt.com)++)  
8. *Explainable artificial intelligence for cybersecurity: A literature survey*. (2022). Annals of Telecommunications. (++[Springer](https://link.springer.com/article/10.1007/s12243-022-00926-7?utm_source=chatgpt.com)++)  
9. Vassilev, A., Oprea, A., Fordyce, A., & Andersen, H. (2024). *Adversarial Machine Learning: A Taxonomy and Terminology of Attacks and Mitigations*. NIST AI 100-2. (++[NIST](https://www.nist.gov/publications/adversarial-machine-learning-taxonomy-and-terminology-attacks-and-mitigations?utm_source=chatgpt.com)++)  
10. Zhang, J., Bu, H., Wen, H., Liu, Y., et al. (2025). *When LLMs meet cybersecurity: A systematic literature review*. Cybersecurity, 8, 55. (++[DOI](https://doi.org/10.1186/s42400-025-00361-w?utm_source=chatgpt.com)++)  
11. *Large Language Models in Cybersecurity: A Survey of Applications, Vulnerabilities, and Defense Techniques*. (2025). AI, 6(9), 216. (++[DOI](https://doi.org/10.3390/ai6090216?utm_source=chatgpt.com)++)  
12. Das, B. C., Amini, M. H., & Wu, Y. (2025). *Security and Privacy Challenges of Large Language Models: A Survey*. ACM Computing Surveys, 57(6), Article 152. (++[DOI](https://doi.org/10.1145%2F3712001?utm_source=chatgpt.com)++)  
13. Tabassi, E. (2023). *Artificial Intelligence Risk Management Framework (AI RMF 1.0)*. National Institute of Standards and Technology. (++[NIST](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-ai-rmf-10?utm_source=chatgpt.com)++)  
14. Dunmore, A., Jang-Jaccard, J., Sabrina, F., & Kwak, J. (2023). *A Comprehensive Survey of Generative Adversarial Networks (GANs) in Cybersecurity Intrusion Detection*. IEEE Access. (++[ResearchGate](https://www.researchgate.net/publication/372404301_A_Comprehensive_Survey_of_Generative_Adversarial_Networks_GANs_in_Cybersecurity_Intrusion_Detection?utm_source=chatgpt.com)++)  
15. *Large language models for cyber resilience: A comprehensive review, challenges, and future perspectives*. (2025). Applied Soft Computing, 170, 112663. (++[ScienceDirect](https://www.sciencedirect.com/science/article/pii/S1568494624014376?utm_source=chatgpt.com)++)  
  
## Suggested Figures and Tables for the Final Report  
## Figure 1 — AI Cybersecurity Ecosystem  
Place in **Section 1**.  
Show:  
**AI/ML → Threat Detection → Analysis → Response → Recovery**  
with applications such as IDS, malware, phishing, CTI and incident response.  
## Figure 2 — Literature Selection Flowchart  
Place in **Section 2**.  
Show:  
**Identification → Screening → Eligibility → Included Studies**  
Use your actual search numbers.  
## Table 1 — Literature Search Strategy  
Place in **Section 2**.  
Include:  
* database;  
* search terms;  
* publication period;  
* results;  
* final selected studies.  
## Figure 3 — AI Across the Cyberattack Lifecycle  
Place in **Section 3**.  
Show:  
**Reconnaissance → Initial Access → Execution → Persistence → Lateral Movement → Detection → Response → Recovery**  
Then indicate where AI contributes.  
## Table 2 — AI/ML Model Comparison  
Place in **Section 4**.  
Use the model comparison table provided above.  
## Table 3 — AI vs Traditional Cybersecurity  
Place in **Section 5**.  
Use the comparison table provided above.  
## Figure 4 — Adversarial Machine Learning  
Place in **Section 6**.  
Show:  
**Attacker → Manipulated Data/Input → AI Model → Incorrect Prediction → Security Failure**  
## Figure 5 — AI as Defender vs AI as Attacker  
Place in **Section 7**.  
Left side:  
**AI for Defence**  
* threat detection;  
* malware analysis;  
* phishing detection;  
* incident response.  
Right side:  
**AI for Attack**  
* phishing generation;  
* reconnaissance;  
* vulnerability discovery;  
* attack automation.  
## Figure 6 — Explainable AI Workflow  
Place in **Section 8**.  
Show:  
**Security Data → AI Model → Prediction → SHAP/LIME → Explanation → Analyst → Decision**  
## Table 4 — Research Gap Matrix  
Place in **Section 9**.  

| Area | Current Literature | Limitation | Research Gap |
| -------- | --------------------------- | ---------------------------- | ----------------------------- |
| IDS | Strong experimental results | Dataset dependence | Real-world validation |
| Malware | DL performs well | Generalisation | Cross-dataset testing |
| Zero-day | Anomaly detection promising | Limited data | Adaptive detection |
| XAI | Better transparency | Computational cost | Real-time XAI |
| FL | Privacy benefits | Communication/security risks | Secure large-scale FL |
| LLMs | Strong analytical potential | Hallucination/prompt attacks | Reliable cybersecurity agents |
  
## Final Research Position  
The central argument of the report should be:  
**AI is transforming cybersecurity by enabling more adaptive, scalable and automated threat detection and response. However, AI does not eliminate traditional cybersecurity limitations; instead, it introduces new challenges involving data quality, explainability, adversarial manipulation, computational requirements and AI-enabled attacks. Therefore, the future of cybersecurity is likely to depend on a hybrid approach combining traditional controls, AI/ML, trustworthy AI principles and human expertise.**  
  
  
  
  
## Table of Abbreviations and Full Forms  
Based on the terminology used in your report, you can include the following **“List of Abbreviations”** near the beginning of the report, after the Table of Contents.  

| Short Form | Full Form |
| ------------ | ------------------------------------------------------------------------------------------------------------ |
| AI | Artificial Intelligence |
| ML | Machine Learning |
| DL | Deep Learning |
| RL | Reinforcement Learning |
| DRL | Deep Reinforcement Learning |
| LLM | Large Language Model |
| LLMs | Large Language Models |
| IoT | Internet of Things |
| IDS | Intrusion Detection System |
| SIDS | Signature-based Intrusion Detection System |
| DDoS | Distributed Denial-of-Service |
| APT | Advanced Persistent Threat |
| APTs | Advanced Persistent Threats |
| AML | Adversarial Machine Learning |
| XAI | Explainable Artificial Intelligence |
| GAN | Generative Adversarial Network |
| GANs | Generative Adversarial Networks |
| CNN | Convolutional Neural Network |
| GRU | Gated Recurrent Unit |
| PCA | Principal Component Analysis |
| SHAP | SHapley Additive exPlanations |
| LIME | Local Interpretable Model-agnostic Explanations |
| GPT | Generative Pre-trained Transformer |
| BERT | Bidirectional Encoder Representations from Transformers |
| AI/ML | Artificial Intelligence / Machine Learning |
| CNN+GRU | Convolutional Neural Network + Gated Recurrent Unit |
| PODCNN-LWID | Lightweight Intrusion Detection approach based on PODCNN (use the exact expansion given in the source paper) |
| CPU | Central Processing Unit |
| RAM | Random Access Memory |
| XAI | Explainable Artificial Intelligence |
| IT | Information Technology |
| 5G | Fifth Generation Mobile Network |
| Industry 5.0 | Fifth Industrial Revolution / Industry 5.0 |
| Zero Trust | Zero Trust Security Architecture |
| LLM Security | Large Language Model Security |
| IDS | Intrusion Detection System |
| MITRE ATT&CK | MITRE Adversarial Tactics, Techniques, and Common Knowledge |
  
**Recommended title for this part of your report**  
**List of Abbreviations**  
Place it **after the Table of Contents and before the Abstract**.  
One important point: for abbreviations such as **PODCNN-LWID**, don't invent the full form. Use the exact expansion from the original research paper you cited.  
  
  

| No. | Study | Main Focus | AI/ML Approach | Key Findings | Limitations / Research Gap | Contribution to This Review |
| --- | ------------------------------ | ----------------------------------- | ------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| 1 | Bomboy (2025) [54] | ML vs. DL for intrusion detection | ML and DL models, including CNN+GRU | CNN+GRU demonstrated strong detection performance, with reported accuracy of up to 99%across the evaluated datasets. | Results may depend on dataset characteristics; real-world scalability and generalisation require further investigation. | Provides comparative evidence for selecting effective DL architectures for cybersecurity. |
| 2 | Yang et al. (2024) [55] | DRL for network security | Deep Reinforcement Learning (DRL) | DRL is promising for dynamic security environments and autonomous defence decisions. | Training complexity and data imbalance remain significant challenges. | Supports the potential of AI-driven autonomous and adaptive cyber defence. |
| 3 | Shaukat et al. (2020) [60] | ML applications in cybersecurity | ML techniques for spam, malware and intrusion detection | ML has become an important cybersecurity technique but can itself be exploited by adversaries. | Limited robustness against adversarial manipulation remains a concern. | Establishes the broader development and security challenges of ML-based cybersecurity. |
| 4 | Dhanushkodi et al. (2024) [62] | AI-enabled threat detection | AI/DL and GANs | GANs can generate synthetic attack samples and help address imbalanced cybersecurity datasets. | Synthetic data may not fully represent the complexity of real-world attacks. | Demonstrates how generative AI techniques can improve cybersecurity model training. |
| 5 | Ozkan-Okay et al. (2024) [63] | AI/ML efficiency and cybersecurity | ML, DL, RL and Generative AI | AI tools such as ChatGPT provide defensive opportunities but also introduce dual-use and security risks. | GenAI security, misuse and reliability require further research. | Connects conventional AI/ML cybersecurity research with emerging generative AI technologies. |
| 6 | He et al. (2023) [18] | Adversarial ML in NIDS | Adversarial Machine Learning | The review identifies significant attention to adversarial attacks, particularly white-box attacks, while mitigation remains less developed. | Defensive strategies against adversarial attacks are still insufficient. | Directly supports the review's analysis of AI model security and adversarial resilience. |
| 7 | Sowjanya et al. (2026) [34] | Early intrusion detection | Feature-reduced ML, including SVM and KNN | Feature reduction can reduce computational requirements while maintaining useful detection performance. | Further validation is needed for highly dynamic and large-scale environments. | Demonstrates how lightweight AI can address resource constraints in cybersecurity deployment. |
| 8 | Wiafe et al. (2020) [68] | AI research trends in cybersecurity | Systematic mapping of AI/ML techniques | SVM was widely used, with research heavily concentrated on IDS/IPS applications. | Greater exploration of emerging AI techniques is required. | Provides evidence of the evolution from traditional ML toward newer AI architectures. |
| 9 | Neupane et al. (2022) [76] | Explainable intrusion detection | XAI, SHAP and LIME | XAI can improve the interpretability and trustworthiness of AI-based IDS decisions. | Real-time explanation and computational efficiency remain challenging. | Supports the importance of explainability for human-centred cybersecurity operations. |
| 10 | Kheddar (2024) [52] | Transformers and LLMs for IDS | BERT, GPT and Transformer models | Transformer and LLM approaches offer promising capabilities for analysing complex security data and improving IDS. | Computational cost, retraining limitations and security risks remain concerns. | Establishes LLMs and Transformers as an important emerging direction in AI-driven cybersecurity. |
  
