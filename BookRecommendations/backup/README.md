## Disclaimer

This is a learning project. I am not an experiences data scientist. I've got following feedback to this version of a solution of book recommendation problem:

Positives:
- data-preprocessing - all main traps in data were caught (bad format of ISBNs, bad format of book titles)
- creative idea with expanding book metadata from wikipedia data
- simple recommender in shape of input field

Negatives
- working with implicit ratings
  - The boxplots of the average rating were in the range 0 - 6, where the median was below 5. This was unfortunately caused by the fact that I was working with implicit ratings, which was one of the main elements of the task.
- data normalization
  - Ratings are in fact serial discrete variables, i.e. their order can be recognized and the "transformation" into a centralized continuous distribution is wrong. In general, normalization is a good idea, unfortunately one really has to be careful if it can really be applied to the data
- use of correlation
  - The same is basically true for the applied correlation. In this case, it was not a completely bad idea, but there are many traps behind the correlation - e.g. Highly correlated books can also be those from a completely different genre (such as a book by Rosamund Pilcher and The Lord of the Rings), because these books have been evaluated by a large number of users from the same country and the correlation itself will not reveal this to you.
- key element of the task was missing
  - If someone puts a LOTR book in mu recommender - what would they recommend? I did not follow the assignment  (Problem: Book recommendations - "I like Lord of the Rings, what else should I read?").

## I like Lord of the Rings, what else should I read?

Recommendation systems are everywhere. Companies are relying on them to get better sales. We, as consumers, are relying on them to navigate us through vast space of possibilities. We are tired on deciding between many options and we just want to describe few things we like and system would pick the perfect match for us.

This project is about trying some recommendation systems approaches to build a book recommendation model.

To get some book recommendations, open [IBCF_page notebook](IBCF_page.ipynb) in Colab and run it.

## Content

- [data/](data)
  - preprocessed data and model
- [IBCF_page.ipynb](IBCF_page.ipynb) 
  - interactive demonstration of books recommendation system using item-based collaborative filtering created in [item_basedCF.ipynb](item_basedCF.ipynb). Run this notebook in Google Colab (or locally) to see interactive application.
- [ideas.md](ideas.md)
  - thoughts and questions about things that could be done. But were not.
- [data_preprocessing.ipynb](data_preprocessing.ipynb) 
  - finalized data preprocessing pipeline.
- [item_basedCF.ipynb](item_basedCF.ipynb) 
  - creating item-based collaborative filtering recommendation model from data preprocessed in [data_preprocessing.ipynb](data_preprocessing.ipynb).
- [playground.ipynb](playground.ipynb) 
  - trying various paths before building final model.
- [research.ipynb](research.ipynb) 
  - notes during research.
