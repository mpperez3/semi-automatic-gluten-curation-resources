# A deep learning relation extraction approach to support a biomedical semi-automatic curation task: the case of the gluten bibliome  
****

Martín Pérez-Pérez 1,2 [0000-0003-1349-6562]*, Tânia Ferreira 3,4 [0000-0002-3974-0474], Gilberto Igrejas 3,4,5 [0000-0002-6365-0735], Florentino Fdez-Riverola 1,2 [0000-0002-3943-8013]

- 1 CINBIO, Universidade de Vigo, Department of Computer Science, ESEI - Escuela Superior de Ingeniería Informática, 32004 Ourense, España.
- 2 SING Research Group, Galicia Sur Health Research Institute (IIS Galicia Sur), SERGAS-UVIGO, Spain
- 3 Department of Genetics and Biotechnology, University of Trás-os-Montes and Alto Douro, Vila Real, Portugal
- 4 Functional Genomics and Proteomics Unit, University of Trás-os-Montes and Alto Douro, Vila Real, Portugal
- 5 LAQV-REQUIMTE, Faculty of Science and Technology, Nova University of Lisbon, Lisbon, Portugal

****

**Background**. Discover relevant biomedical interactions in the literature is crucial for enhancing biology research. It has an essential role in studying the different processes and interactions reported that affect the biological process (e.g., genome, metabolome, and transcriptome). Therefore, the objective of this work is twofold: reduce the manual effort required to curate and review the existing biochemical interactions reported in the gluten-related bibliome while proposing a novel relation extraction deep learning approach that assists in a real curation task by learning from the previous decisions of the curators.

**Methods**. Compared to previous works, the main contribution of this work lies in proposing a deep learning model that incorporates a novel vector-space that combine (_i_) high-level lexical and syntactic inference features as Wordnets and Health-related domain ontologies, (_ii_) unsupervised domain syntactic and semantic resources as word embeddings, (_iii_) semantical and sentence structure knowledge (e.g., part of speech, negation information, verb information), (_iv_) abbreviation resolution support, (_v_) several state-of-the-art Named-entity recognition methods, and (_vi_) different feature construction and optimization techniques to support a semi-automatic curation workflow.

**Results**.The application of the semi-automatic curation workflow over a classified set of 2,451 relevant gluten-related documents produces a total of 8,349 relevant relations and 471,813 irrelevant relations of the next relation categories: (_i_) Related health issue, (_ii_) Improve, (_iii_) Aggravate, (_iv_) Stimulation, (_v_) Inhibition, (_vi_) Activation, (_vii_) Deactivation, (_viii_) Downregulation, (_ix_) Upregulation, (_x_) increase symptoms, (_xi_) decrease symptoms, (_xii_) weak relation and (_xiii_) no effect. Therefore, the mean achieved F-score for the different relation categories established was 0.731, with the lowest F.score at 0.47 (with 200 positive identified relations) and the highest F.score at 0.929 (with 2,129 positive identified relations).
Experimental results showed that the presented workflow is an excellent approach for a semi-automatic RE task. It was able to obtain satisfactory results in the early stages of a real-world curation task and saved manual annotation efforts by learning from the decisions made by manual curators. On the other hand, the presented sentence vector-space can be integrated into several state-of-the-art machine learning models to recognize relevant relations with satisfactory results. Finally, this work highlights the benefit of use domain knowledge as ontologies and entity recognizers to improve the automatic recognition of health-related interactions in the literature.


## Data 
****
- **AbbreviationDictionary_domain**: Contains the abbreviation resolution rules 
- **englishCommonStopWords**: A simple list of common stop words used to annotate pre-process the sentences
- **lexicon**: The complementary parsed lexicon used to discover relevant entities and normalized the identified words stored in a SQL database
- **relation_rulesV10.json**: Relation definition and probabilities taking into account the possible entities that interact. 
- **relationDatasetBaseline**: Curated relation corpus. Identified negative and positive sentences that contains (or not) a possible relevant interaction
- **relationDatasetProcessed**: Pre-processed curated relation space before applying the proposed vector-space construction techniques. 
  (contains the sentence text, the recognized annotations by the different named entity recognisers, the verb information, the PoS information... this file avoids the processing of the baseline dataset with the third parties libraries used as Dnorm,LINNAEUS, Stanford CoreNLP, etc to process the baseline sentence dataset)
- **stopWords**: A complementary curated list of the task stop words
- **word2vec_MyDictionary**: TSV serialization of the unsupervised Word2Vec space used to normalize the sentences and training against using the gluten-related literature

## License
****

Academic Free License v3.0