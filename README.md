E2E Evaluation metrics
======================

Adapted from MT-Eval + COCO Caption Evaluation scripts. A convenient way of running all of them 
will appear soon.

MT-Eval
-------

We used the NIST MT-Eval v13a script adapted for significance tests, from 
<http://www.cs.cmu.edu/~ark/MT/>.
We adapted the script to allow a variable number of references:
* Create .sgm files with the maximum number of references available for any instance
* Keep some of the references empty

The NIST and BLEU brevity penalties are adjusted to ignore empty reference texts.


Microsoft COCO Caption Evaluation scripts
-----------------------------------------

These provide a different variant of BLEU (not used here), METEOR, ROUGE-L, CIDER.

## Requirements ##
- java 1.8.0
- python 2.7

## Files ##
./
- cocoEvalCapDemo.py (demo script)

./annotation
- captions_val2014.json (MS COCO 2014 caption validation set)
- Visit MS COCO [download](http://mscoco.org/dataset/#download) page for more details.

./results
- captions_val2014_fakecap_results.json (an example of fake results for running demo)
- Visit MS COCO [format](http://mscoco.org/dataset/#format) page for more details.

./pycocoevalcap: The folder where all evaluation codes are stored.
- evals.py: The file includes COCOEavlCap class that can be used to evaluate results on COCO.
- tokenizer: Python wrapper of Stanford CoreNLP PTBTokenizer
- bleu: Bleu evalutation codes
- meteor: Meteor evaluation codes
- rouge: Rouge-L evaluation codes
- cider: CIDEr evaluation codes

## References ##

- [Microsoft COCO Captions: Data Collection and Evaluation Server](http://arxiv.org/abs/1504.00325)
- PTBTokenizer: We use the [Stanford Tokenizer](http://nlp.stanford.edu/software/tokenizer.shtml) which is included in [Stanford CoreNLP 3.4.1](http://nlp.stanford.edu/software/corenlp.shtml).
- BLEU: [BLEU: a Method for Automatic Evaluation of Machine Translation](http://www.aclweb.org/anthology/P02-1040.pdf)
- Meteor: [Project page](http://www.cs.cmu.edu/~alavie/METEOR/) with related publications. We use the latest version (1.5) of the [Code](https://github.com/mjdenkowski/meteor). Changes have been made to the source code to properly aggreate the statistics for the entire corpus.
- Rouge-L: [ROUGE: A Package for Automatic Evaluation of Summaries](http://anthology.aclweb.org/W/W04/W04-1013.pdf)
- CIDEr: [CIDEr: Consensus-based Image Description Evaluation] (http://arxiv.org/pdf/1411.5726.pdf)

## Developers ##
- Xinlei Chen (CMU)
- Hao Fang (University of Washington)
- Tsung-Yi Lin (Cornell)
- Ramakrishna Vedantam (Virgina Tech)

## Acknowledgement ##
- David Chiang (University of Norte Dame)
- Michael Denkowski (CMU)
- Alexander Rush (Harvard University)
