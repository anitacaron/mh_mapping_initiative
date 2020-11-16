# Mouse-Human Phenotype Mapping Initiative (MHMI)

Studying the phenotypic effects of genes is critical to understanding disease. The phenotypic effects of variants and lesions in large numbers of mouse genes are known due to the accumulated small-scale efforts of the mouse genetics community combined with a large amount of data from genome-wide gene targeting combined with systematic phenotyping. This data can be leveraged to help understand phenotypes not only in mice, but also in humans. A key component required for the integration of human and mouse phenotype data is meaningfully linking the dominant controlled vocabularies (ontologies) used for describing phenotype. For human data the Human Phenotype Ontology is widely used, while for mouse (and rat) data, the Mammalian Phenotype ontology is typically used. 

There are roughly three categories of such mapping approaches:
- __Manually curated:__ An expert translates a set of terms from one terminology into another.
- __Automated mapping:__ A mapping algorithm takes two or more vocabularies as an input and attempts to create cross-vocabulary links between the terms by using a variety of approaches, from terminological mappings (e.g. base on label, natural language information) to graph-based approaches.
- __Computable phenotype definitions:__ Experts define the phenotypes they are using (for example in the Human Phenotype Ontology) using standardised design patterns. Definitions developed this way are interoperable across species. Examples include: the Unified Phenotype Ontology and Phenome.NET.

The first complication of all these are approaches is that they are _error prone_ for different reasons. The most important reasons are:
1. _Experts make mistakes_ - both when manually mapping and when defining computable phenotype definitions. Often this is due to ambiguity and variation in the use of language to describe phenotypes.
2. Some _assumptions_ are made during the mapping process, for example: 
   - How "rough/vague" a mapping is still acceptable in my case, if an exact match cannot be found (this differs from use case to use case)? Should Fever be mapped to increased body temperature?  Should Shivering be mapped to tremors?
   - Should I define my phenotype in terms of a physical measurement or observation  or in terms of an abnormal biological process (abnormally increased levels of insulin vs abnormally increased insulin production)? 

Furthermore, analysts may expect mappings to different degrees of fuzziness - from crisp 1:1 mappings to n:n mappings determined by phenotypic similarity.

The MHMI aims to collect and standardise the dissemination of mouse-phenotype mappings and develop a set of best practices for their use. If you are interested in taking part in the Initiative or have use cases that you feel would benefit from these mappings, feel free to join the [Monarch Initiative \& Friends Mailing list](https://groups.google.com/g/monarch-friends) and drop us a message. 

Current active/prospective participants include:

| Name | Institution | Role |
| ---- | ----------- | ----- |
| David Osumi-Sutherland | EMBL-EBI, Monarch Initiative | coordinator, semantics specialist |
| Susan Bello | JAX, MGI, Alliance of Genome Resources | coordinator, ontology engineer, bio-curator |
| Nicolas Matentzoglu | EMBL-EBI, Monarch Initiative | coordinator, semantic engineer |
| Ben Stear | Department of Biomedical and Health Informatics, Children's Hospital of Philadelphia | Bioinformatics Scientist I |
| Deanne Taylor | Department of Biomedical and Health Informatics, Children's Hospital of Philadelphia | Director of Bioinformatics |
| Francisco Requena | Institut Imagine (Paris) | Ph.D. Student at the Clinical Bioinformatics lab |
| Justin Reese | Lawrence Berkeley Lab | Computational Biologist |
| Li Xiaoxu | Laboratoire de Physiologie Intégrative et Systémique (EPFL) | |
| Violeta Munoz Fuentes | EMBL-EBI, IMPC | |


## Specific goals

### Collecting all manually curated MP-HP mappings in one place and offering them in a standard format

- Many manual mappings between MP and HP have been performed for various purposes (COVID (MGI effort), IMPC knockouts, HPO, MPO xrefs, HMDC phenotype headers (MGI Effort))
- During our uPheno evaluation efforts, we often review automated mapping based on logical inferences. There should be a separate effort to store manually reviewed mappings of automated approaches, which we could use for validation -> when previously validated inferences suddenly disappear, etc.
We will offer these manually curated mappings in a standard format (SSSOM)

Sub goals:
- Tightly align the upper levels of HP/MP to be able to provide some sanity checking for automated approaches.

### Build a conceptual and empirical model for using various forms of automated mappings for stakeholder use cases

- We will offer a range of automated mappings, from label based, EQ based to semantic similarity and traditional automated mapping approaches using the approaches explored by the OAEI.
- We will document their use cases carefully, and offer simple python notebooks for example evaluations.
- We will develop a model on how to evaluate the effectiveness of automated mapping approaches for the use cases provided by our stakeholders.
- We will determine the set of interventions needed to gradually improve automated approaches in a scalable and sustainable way.

### Build infrastructure to combine automated and manually curated mappings

- There is a huge potential in using automated approaches to validate manual curations. For example, manual mappings could be compared to semantic similarity mappings, with a low semantic similarity indicating problematic choices.
- On the flipside, expert-level mappings can be used as gold standards to evaluate automated mapping approaches. Such information can lead directly to tweaks in the mapping algorithms, but also indicate areas in the ontology that could benefit from more careful axiomatisation or reconciliation.

### Initial stakeholder use cases in focus of working group

- Increasing the clinical relevance of search results on mouse-phenotyping.org (IMPC) of mouse phenotyping in general
- Variant prioritisation 
   - for diagnosis of children with developmental disorders (CHOP)
   - of rare disease patients (Exomiser)


## Stakeholder use cases for mouse-phenotype mappings using ontologies

*Ben Stear*, Bioinformatics Scientist I, Department of Biomedical and Health Informatics, Children's Hospital of Philadelphia: 

> Our main use case is to identify genes of interest from children with cancer/structural birth defects. When a child comes in with a birth defect we want to be able to map their phenotype(s) to the corresponding mouse phenotype(s) in order to take advantage of the extensive gene-knockout research that's been done in mice. Once we have identified the corresponding mouse phenotype, we can then identify genes associated with that phenotype, and then from there get a list of human orthologs for further analysis. 


*Francisco Requena*, Ph.D. Student at the Clinical Bioinformatics lab, Institut Imagine (Paris):

> My work consists of the interpretation of the mutations found in the DNA of patients with genetic diseases. Phenotypic similarity analysis allows us to take advantage of patients' clinical features to find the causal gene(s). Unfortunately, hundreds of new associations of genetic diseases are discovered every year. Therefore, our current knowledge about the associations of HP terms and genes is limited. As an alternative, we have available extensive information on the effect of altered genes in mouse models with their respective phenotypical consequences. For those genes without HP term annotation, an interesting approach is semantic similarity between MP terms (mouse model) and HP terms (patient).


*Li Xiaoxu*, Laboratoire de Physiologie Intégrative et Systémique (EPFL)

> My project revolves around using our large datasets in mouse genetic reference populations (https://www.systems-genetics.org/, PMID: 29199021) to infer information about humans. One important step in this procedure is matching the many phenotypes we measured in the mice to their human equivalents, hence my interest.


