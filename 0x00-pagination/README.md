# Pagination

This project implements pagination techniques for handling large datasets efficiently. It demonstrates various approaches to pagination including simple pagination, hypermedia pagination, and deletion-resilient pagination.

## Background Context

When working with large datasets, it's impractical to return all records at once. Pagination allows for breaking down data into manageable chunks while providing a way to navigate through the entire dataset.

This project uses a dataset of popular baby names (from `Popular_Baby_Names.csv`) to demonstrate pagination techniques.

## Learning Objectives

- How to paginate a dataset with simple page and page_size parameters
- How to paginate a dataset with hypermedia metadata
- How to implement deletion-resilient pagination

## Files and Functionality

### 0-simple_helper_function.py

Contains a helper function `index_range(page, page_size)` that calculates the start and end indices for pagination:
- Takes page number and page size as arguments
- Returns a tuple of (start_index, end_index)
- Pages are 1-indexed (first page is page 1)

### 1-simple_pagination.py

Implements a `Server` class with simple pagination functionality:
- Loads data from the CSV file
- Provides a method `get_page(page, page_size)` that returns the appropriate slice of data
- Validates input parameters
- Returns empty list for out-of-range requests

### 2-hypermedia_pagination.py

Extends the `Server` class with hypermedia pagination:
- Implements a `get_hyper(page, page_size)` method that returns a dictionary with:
  - `page_size`: Number of records in the page
  - `page`: Current page number
  - `data`: Page data (dataset records)
  - `next_page`: Number of the next page (or None)
  - `prev_page`: Number of the previous page (or None)
  - `total_pages`: Total number of pages in the dataset

### 3-hypermedia_del_pagination.py

Implements deletion-resilient pagination:
- Handles cases where data might be deleted between pagination requests
- Includes `get_hyper_index(index, page_size)` method that returns:
  - `index`: Current start index
  - `next_index`: Next index to query
  - `page_size`: Current page size
  - `data`: Actual page data
- Ensures users don't miss items when data is deleted between requests

## Requirements

- Python 3.7 (interpreted on Ubuntu 18.04 LTS)
- PyCodeStyle 2.5.*
- All files end with a new line
- First line of all files: `#!/usr/bin/env python3`
- All modules, functions, and methods include documentation
- All functions and coroutines are type-annotated

## Usage

Each file can be executed directly to test its functionality with the included main files.

Example:
```bash
./0-main.py
./1-main.py
./2-main.py
./3-main.py
```

## Dataset

The project uses `Popular_Baby_Names.csv`, a dataset containing information about popular baby names including:
- Year of Birth
- Gender
- Ethnicity
- Child's First Name
- Count
- Rank
