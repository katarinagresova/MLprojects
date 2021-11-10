## Data preparation

- Download metadata for books that are in `ratings` table, but are not in `books` table.
    - Function for this is already prepared in [playground.ipynb](playground.ipynb) notebook under section _Missing books records_.
- In general, get better and more metadata for books, if we can. This is a part where we might be able to improve quality of metadata, nut we are not able to get better metadata for users. Things to look at:
    - non-unicode characters in foreign books,
    - titles not properly cleaned after scrapping,
    - better merging of duplicities in table `books`,
    - manually fix few ISBN numbers with typos,
    - add feature *language* to books - there are many different languages in dataset.
- Data description: what is source of implicit rating? How to work with it?
- What type of rating normalization to use?
- How can we validate, that we made valid preprocessing operations and information in data is not corrupted?

## Models

- User-item matrix for large datasets:
    - `pivot_table()` and `corr()` from `pandas` is solution only for very small dataset (just around 5k books after preprocessing in our case).
- Use information from cover image in computing similarity between books.
