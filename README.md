# Benchmark datasets for keyphrase extraction

This repository contains a large, curated set of benchmark datasets for
evaluating automatic keyphrase extraction algorithms. These datasets are all
pre-processed using the Stanford CoreNLP suite and are available in XML format.

## Dataset format

All datasets are stored according to the following, common structure:

    dataset/
           /test/       <- test documents
           /train/      <- training documents (if available)
           /dev/        <- validation documents (if available)
           /src/        <- everything used to build the dataset
           /references/ <- reference keyphrases in json format

## Reference (gold annotation) format

Reference keyphrases, used for evaluating automatic keyphrase extraction
algorithms, are available in json format and named according to the following
rules: `[split].[annotator].[stem]?.json`

where

* `split` corresponds to the dataset split: test, train or dev
* `annotator` is the type of annotation: author, reader, combined, contr (controlled vocabulary), uncontr (free annotation)
* `stem` (optional) indicates that stemming (using nltk Porter algorithm) is applied on reference keyphrases.

Below is a an example of reference file format:

    {
        "doc-1": [
            [
                "target detect"
            ],
            [
                "number of sensor",
                "sensor number"
            ]
        ],
        ...
    }

## Available datasets

| dataset                | lang | nature       | train | dev | test | gold              |
| ---------------------- | ---- | ------------ | -----:| ---:| ----:| -----------------:|
| CSTR [1]               | en   | Full papers  | 130   | -   | 500  | authors           |
| DUC-2001 [3]           | en   | News         | -     | -   | 308  | readers           |
| Inspec [2]             | en   | Abstracts    | 1000  | 500 | 500  | indexers          |
| ACM [4]                | en   | Abstracts    | -     | -   | 2304 | authors           |
| SemEval-2010 [7]       | en   | Full papers  | 144   | -   | 100  | authors, readers  |
| 500N-KPCrowd [5]       | en   | News         | 450   | -   | 50   | readers           |
| Wikinews-Keyphrase [6] | fr   | News         | -     | -   | 100  | readers           |

## References

1. **KEA: Practical automatic keyphrase extraction.**
   Witten, I. H., Paynter, G. W., Frank, E., Gutwin, C., & Nevill-Manning, C. G.
   *In Proceedings of the fourth ACM conference on Digital libraries.*
   p. 254-255. 1999.

2. **Improved automatic keyword extraction given more linguistic knowledge.**
   Anette Hulth.
   *In Proceedings of EMNLP 2003.*
   p. 216-223.

3. **Single Document Keyphrase Extraction Using Neighborhood Knowledge.**
   Xiaojun Wan and Jianguo Xiao.
   *In Proceedings of AAAI 2008.*
   pp. 855-860.

4. **Large dataset for keyphrases extraction.**
   Krapivin, M., Autaeu, A., & Marchese, M. (2009). 
   *University of Trento.*

5. **Supervised Topical Key Phrase Extraction of News Stories using
   Crowdsourcing, Light Filtering and Co-reference Normalization.**
   Marujo, L., Gershman, A., Carbonell, J., Frederking, R., & Neto, J. P.
   *In Proceedings of LREC 2012.*

6. **TopicRank: Graph-Based Topic Ranking for Keyphrase Extraction.**
   Adrien Bougouin, Florian Boudin, Béatrice Daille.
   *In Proceedings of the International Joint Conference on Natural Language
   Processing (IJCNLP), 2013.*

7. **How Document Pre-processing affects Keyphrase Extraction Performance.**
   Florian Boudin, Hugo Mougard and Damien Cram.
   *COLING 2016 Workshop on Noisy User-generated Text (WNUT).*