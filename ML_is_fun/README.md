# Tutorial on NLP
Thanks to Adam Geitgey for [this tutorial](https://medium.com/@ageitgey/natural-language-processing-is-fun-9a0bff37854e)

## Set-up
```shell
pip3 install -U spacy
python3 -m spacy download en_core_web_lg
pip3 install -U textacy
```

For step 2, get FastText
```shell
git clone https://github.com/facebookresearch/fastText.git fast_text
cd fast_text
make
pip3 install .
cd ..
```
Also need to get the [Yelp dataset](https://www.yelp.com/dataset/download) and store it the `data/` directory.

Then:
```shell
python3 convert_yelp_data.py
./fast_text/fasttext supervised -input training/fasttext_dataset_train.txt \
                                -output training/reviews_model
./fast_text/fasttext test training/reviews_model.bin training/fasttext_dataset_test.txt
```