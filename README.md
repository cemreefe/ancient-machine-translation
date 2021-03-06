![img](https://github.com/cemreefe/ancient-machine-translation/blob/master/media/cuneiform.gif?raw=true)

# Machine Translation for Ancient Languages
> In this repository I'll play around with the idea of using machine translation techniques to perform translations to and from ancient languages including Akkadian, Ancient Greek, Ancient Egyptian etc.

### Why?
I have searched on the web for a machine translation service to help me translate some stuff to Ancient Greek, only to find no such service exists.

That got me thinking, why is there no machine translation service for any ancient languages other than Latin? The reason probably is simple, **there is not enough data**.

Even though there is a great chance I will not succeed I wanted to take my chances. Even if I don't manage to get it working I can learn more about **scraping** disorganized data, **NLP** techniques and working with ancient languages.

### Work so far

- Set up a jupyter notebook to parse **Akkadian** sentence and pairs from [ETCSL corpus](http://etcsl.orinst.ox.ac.uk/cgi-bin/etcsl.cgi?text=all#). 
Some of the problems I encountered in the process were

    - A lot of tablets have missing lines, so there are gaps inside the sentences.
    - The akkadian sentences are organized in lines, not sentences. So the sentence endings are not marked 
    - Some translations are given in batches. (Translation of a passage from the 49th line to the 56th line might be given as one translation block, namely "49-56.") With sentences not being seperated by any means, the only way to pair the translation with the original Akkadian sentences is to concatenate the corresponding sentences. This results in "sentences" of up to 1000 tokens. This seriously harms the performance of a model trying to learn from this data.