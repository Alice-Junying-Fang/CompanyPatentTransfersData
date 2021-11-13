# This repository contains python codes of developing new Company-Level Database of Meaningful Patent Transfers with Company Permnos

<details>
<summary><strong><em>Table of Contents</em></strong></summary>

- [Overview](#overview)
  - [New Data Source](#new-data-source)
  - [Methodology](#methodology)
- [Results](#results)
  - [TFP Growth](#tfp-growth)
  - [GDP Growth](#gdp-growth)

</details>

# Overview

## Parse XML Format of USPTO Patent Transfers
XML format of raw USPTO patent transfers data at the patent property level is parsed into CSV format of patent transfers at the patent transfer level. 

Note that multiple patent transfers of one patent property may be updated at the same date. Thus, the date + patent id cannot uniquely identify each patent transfer. 

## Identify and Determine Not Meaningful Patent Transfers 
Textual Analysis and Regular Expressions are developed in Python to identify and determine not meaningful patent transfers.

Not Meaningful Patent Transfers:
* Transfers from inventors to their companies: Develop Textual analysis and regular expressions to identify whether the name is company name or person name
* Transfers across subsidiaries of companies: Compare similarities of addresses between patent assignors and assignees to identify this internal transfer

## Preprocess Company Names
Company names are preprocessed and standardized to improve the number of exact matching company names.
* Remove meaningless symbols in company names and trailing spaces
* Convert abbreviations to full names for standardization
* Drop company attributes and stop words

## Texutal Analysis to Improve the Accuracy of Fuzzy Matching Company Names
* Extract unique company identifiers out of company names 
* Develop special algorithm for fuzzy matching short company names 

## Develop Parallelizations to Speed Up Codes
All codes are speeded up by parallelizing operations of Pandas DataFrame and Numpy Arrays.

# Acknowledgement
USPTO Patents Assignments Databse https://www.google.com/googlebooks/uspto-patents-assignments.html
