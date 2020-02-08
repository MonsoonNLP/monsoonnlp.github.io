# A Whole World of BERT
## Multilingual BERT, or language-specific implementations?

### BERT and XLM-R create word embeddings in multiple languages

[In November 2018](https://ai.googleblog.com/2018/11/open-sourcing-bert-state-of-art-pre.html), Google released their NLP library BERT (named after their technique to create pre-trained word embeddings: *Bidirectional Encoder Representations from Transformers*) with English and Chinese models.

Shortly after, the team included models for [Multilingual BERT](https://github.com/google-research/bert/blob/master/multilingual.md) (mBERT), covering 104 languages from around the world.

[In November 2019](https://ai.facebook.com/blog/-xlm-r-state-of-the-art-cross-lingual-understanding-through-self-supervision/), Facebook released XLM-RoBERTa (XLM-R), with two models, one using Masked Language Modeling (MLM, 100 languages), and one combining MLM and Translation Language Modeling (MLM+TLM, 15 languages).

Their analysis shows an improvement over mBERT.

[In December 2019](https://github.com/huggingface/transformers/tree/master/examples/distillation), HuggingFace released DistilmBERT. This ‘distillation’ technique uses a large model to train a much smaller model with similar performance.

This model “reaches 92% of Multilingual BERT’s performance… while being twice faster and 25% smaller.”

### Multi-lingual performance is measured with XNLI

The current standard to measure multilingual language models is the *Cross-Lingual NLI Corpus* (XNLI). This test set in 14 languages (15 when including English) was released by Facebook AI and NYU in September 2018:

> [XNLI](https://www.nyu.edu/projects/bowman/xnli/)

**Who has State of the Art performance on XNLI?**
Currently, both XLM-R models outperform the original mBERT across multiple languages.

![Table of mBERT and XLM models in multiple languages](/images/xnli_table.png)

*performance on XNLI: lg = number of languages, bolded number is best result in language column*

Interestingly, when comparing MLM training on 17 languages or 100 languages, you can see that performance on English and other languages drops. This helps explain why NLP developers will use monolingual or limited language models, instead of always using multilingual models.

### Multilingual models still have language-specific structures

Researchers at Charles University in Prague analyzed which parts of mBERT are language-neutral and language-specific parts. They found that mBERT internally clustered languages into families, and represented similar sentences differently in different languages.

> [How Language-Neutral is Multilingual BERT?](https://arxiv.org/abs/1911.03310)

This helps explain why a multilingual model performs best in a few languages (usually English) rather than developing a language-neutral understanding.
Update: another paper on language relationships and how these are perceived differently based on tokenization (subword, word, character-level): [https://www.aclweb.org/anthology/D19-6106.pdf](https://www.aclweb.org/anthology/D19-6106.pdf)

### Developers make language-specific BERTs to outperform mBERT
In November 2019, researchers at Facebook AI, Inria, and Sorbonne Université published a French monolingual model, with an improvement over mBERT and XLM on the XLNI test. They named it CamemBERT, after a French cheese.

![Table of CamemBERT performance](/images/camembert_table.png)

> [CamemBERT: a Tasty French Language Model](https://arxiv.org/abs/1911.03894)

This is part of an explosion of other language-specific BERTs (some have no match in XLNI, so they use other metrics)

- [German BERT](https://deepset.ai/german-bert), from Deepset.AI, Germany (this predates and was footnoted by CamemBERT)
- [berts](https://github.com/dbmdz/berts/blob/master/README.md) a newer release by *Die Bayerische Staatsbibliothek*, Germany
- [Flaubert](https://github.com/getalp/Flaubert), French, from Getalp, France
- [BETO](https://github.com/dccuchile/beto), Spanish, from *Universidad de Chile*
- [BERTje](https://arxiv.org/abs/1912.09582), Dutch, from *Rijksuniversiteit Groningen*, Netherlands
- [FinBERT](https://arxiv.org/abs/1912.07076), Finnish, from *Turun yliopisto*, Finland
- [AlBERTo](https://github.com/marcopoli/AlBERTo-it), Italian, from *Università degli Studi di Bari Aldo Moro*, Italy
(this predates CamemBERT, but was not as widely shared)
- [GilBERTo](https://github.com/idb-ita/GilBERTo), Italy
- [UmBERTo](https://github.com/musixmatchresearch/umberto), MusixMatch, Italy
- [BERT-Japanese](https://github.com/cl-tohoku/bert-japanese), from 東北大学, Japan
- [Portuguese-BERT](https://github.com/neuralmind-ai/portuguese-bert), from NeuralMind.ai, Brazil
- [RuBERT](https://arxiv.org/abs/1905.07213), Russian, from Физтех, Russia
(this predates CamemBERT, but was not as widely shared)

If [this Twitter thread](https://twitter.com/seb_ruder/status/1221851361811128321) is any indication, more are on the way.
In the meantime, there are alternatives such as the ELMo for Many Languages project from 哈尔滨工业大学, China.

[Search a list of language models here.](http://vectors.nlpl.eu/repository/)

In addition to details mentioned above, another reason that these models can outperform mBERT is that they [can use Whole Word Masking](https://github.com/google-research/bert/issues/873) (WWM), which improved English models in May 2019, but has yet to be available in the 100+ languages of mBERT.

### Language models are available in HuggingFace/Transformers
It was difficult to compile the earlier list, because AI press is focused on large corporations, and there are few places highlighting the universities and startups which publish these models.

One of the key places to share models is through addition to [Transformers](https://github.com/huggingface/transformers).
This library simplifies the process of downloading and using [154 word embeddings](https://huggingface.co/models) in your code. That list includes all of the earlier mentioned models (except Flaubert, which is in a pull request, and RuBERT).

### Many languages are still under-represented

Looking at the top world languages, there are no documented BERT for Arabic, Hindi-Urdu, Malay-Indonesian, Bengali, Punjabi, or Marathi. I hope that these can be created, shown to outperform mBERT on the XNLI (which includes Arabic, Hindi, and Urdu) or another metric, and published through Transformers library.
