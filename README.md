# GA DSI15 Capstone Project: Classifying Authentic and Replica Sneakers

---

### Problem Statement
The sneaker resale market is an estimated 2 billion USD in secondary market in 2019. Estimated to be USD6 billion by 2025 according to research firm, Cowen & Co. Due to the lucrative nature of these commodities, there is the inevitable rise of counterfeits. The counterfeit sneakers sales was USD520 billion or 3.3% in global trade in 2018 and it is costing us in various ways.

The costs to the brands include:
1. Undercutting sales from the brands. Online counterfeit sales are responsible for approximately USD30.3 billion in annual losses to luxury brands, according to data service firm ResearchAndMarkets’ Global Brand Counterfeiting Report.
2. Brands have to deal with the backlash from customers who have had bad experiences from fakes. Additional resources have to be allocated to deal with this
3. Reputation damage

Costs to countries:
1. US Customs and Border Protection (CBP) official stated: "However, these items often fund national and transnational criminal organizations, and cost taxpayers billions. " (Oct 2019)

Costs to collectors:
1. We just want real sneakers man

In light of this, we want to be able to differentiate real and fake sneakers. Our task is to build a classifier that is able to differentiate between real and fake sneakers. Our primary audience will be the sneaker brands and the CBP.

To do so, we will first be scrapping data from reddit and imgur. We will then be using a classification model such as CNN to differentiate between the authentic and the replicas. We will measure our success using several classification metrics including ROCAUC and F1 score.

With this, we also hope to help buyers inform themselves and to stay away from counterfeits. Empowering the public with information, they will be able to make the right decision which could help to reduce the lucrative nature of fake sneakers.

---

### Executive Summary
To combat the increasingly lucrative business of counterfeit sneakers, due to the rise of a sneaker cult following, the goal was to train a Convolutional Neural Network model to classify 2 binary outcome: Authentic or Replica sneakers.

Web scraping was performed to collect a dataset consisting of approximately 20,000 images. The [Data Scraping notebook](./codes/book1_data_scrapping_cleaning.ipynb) can be run periodically to obtain more data over time. Eventually, we came up with a 53/47% split between authentic and replica sneakers respectively.

As the replicas become more and more accurate to the orignals, the shade of colour and size/shape of details (logos, silhouette) on the sneakers are especially important in our case. The choice was made to maintain the RGB (coloured) and aspect ratios of the images, in the preprocessing of the images

Our classifier was successful in predicting at an 0.84 ROCAUC score and F1 score of 0.79. We also chose the F1 score because false positive and false negatives were just as damaging to us.

Overall, there are still areas of improvement but moving forward the first step is definitely to achieve web deployment.

---

### Notebooks:
- [Data Scrapping and Cleaning](./codes/book1_data_scrapping_cleaning.ipynb)
- [Image Selection](./codes/book2a_img_selection.ipynb)
- [Image Preprocessing](./codes/book2b_img_preprocessing.ipynb)
- [Modeling and Recommendations](./codes/book3_preprocesing_modeling_recommendations.ipynb)

---

#### Deliverables
For this project, there will be 3 components:
- 3 x Jupyter notebooks that contains the codes and analysis commentary of the process.
- This README file that provides an introduction to and overview of your project.
- 1 x Presentation slides in pdf format

You can find these here: https://github.com/kennylimyx/sneaker-classifier

---

### Datasets
3 types of datasets in various locations:
- url_all.csv that contains all the links of all the images scraped, can be found in github
- npy files that contains X_train, y_train, X_test, y_test, that can be found here: https://www.dropbox.com/sh/bbwlr20f7mgyua3/AADePfoJiMtnpt9BRrGfNI95a?dl=0
- image files that can be found here: https://www.dropbox.com/sh/zsr6ezblhr1mv5f/AABJFasFtCsHX7LETiX0luSja?dl=0

---
### Conclusions and Recommendations
Our problem statement was to be able to identify authentic vs replicas sneakers in order to combat counterfeit goods. We eventually achieved an ROCAUC score of 86% which is not the best but a good starting point.

Moving forward: Firstly, I will be looking at a web deployment for this classifier. This will help us collate more data and improve the model. Secondly, we can also include images of size tags, receipts and boxes which are frequently used by sneaker authenticators to identify fakes. Lastly, there is a limitation of using images online to authenticate sneakers which is the sense of smell. Smelling the glue in sneakers is often a strong litmus test in identifying replicas.

With the above tool, we can help consumers in their decision making, by presenting them with more information. False negatives will at least drive the consumers/collectors to get a second opinion and could potentially prevent further spread of counterfeit goods. With this tool, there are potential upside and value for both the brands and the BCP.
