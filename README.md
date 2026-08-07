> ## ⚠️ ARCHIVED AND SUPERSEDED, DO NOT USE THIS DATA
>
> This repository is retained only as a historical record of the original
> e-Stat extraction pass. **The dataset published here contains known errors
> and should not be used or cited.**
>
> **Use the `popjp` R package instead:**
>
> * Package: https://github.com/tgyeltshen/popjp
> * Archived release (DOI): https://doi.org/10.5281/zenodo.21830077
>
> ### Known errors in this repository's `poptotal1970_2024lst.RData`
>
> 1. **Gunma is empty.** A prefecture-name mismatch (`Gumma` vs `Gunma`) left
>    the Gunma element of the list as a zero-row data frame, so the entire
>    55-year series for that prefecture is missing.
> 2. **2021 to 2024 counts are roughly half their true value.** The female
>    series was dropped when the annual e-Stat tables were parsed, affecting
>    288 prefecture-year-age cells.
> 3. Counts are in thousands, not persons, and the top age group is stored
>    under the label `age_85_plus` without the collapsed-bin convention that
>    `popjp` documents.
> 4. There is no national aggregate.
>
> All four issues are corrected in `popjp`, which also documents units, the
> collapsed-bin convention, and the provenance of every year.
>
> ### Reproducibility caveat
>
> `totalpop_agegrp_1970_2024.R` is not runnable as published: it hard-codes
> local input paths, relies on fixed spreadsheet row indices, and requires a
> `prefecture-code.xlsx` file that is not included here. The maintained and
> reproducible build lives in `popjp/data-raw/`.

---

**Prefecture-Level Population by Age Group in Japan (1970–2024)**   

This repository provides a harmonized, long-format dataset of population counts by Prefecture × Year × Age Group, covering 1970–2024 for all 47 prefectures in Japan.
Data are extracted, cleaned, and standardized from publicly available statistics provided by e-Stat (the Portal Site of Official Statistics of Japan).

**Key Features**      
✔ 55-year time series (1970–2024)   
✔ Consistent age-group categorization   
✔ Prefecture-level resolution (47 prefectures)   
✔ Total population available for 1970–2024   
✔ Japanese-only population available for 2015–2024 (limited availability before 2015)   

**Data Sources**    
Population statistics were obtained from the following e-Stat datasets:
  Period	Data Source
        1970–2000	Population by Prefecture and Age Group (Census-based)
        2000–2020	Annual Prefecture Population by Sex & Age Group
        2007–2024	Annual Prefecture Total & Japanese Population by Sex
        2010, 2015, 2020	Detailed Census Tables

Links to download raw materials are referenced in the header of the processing script.

All population values are sourced directly from official Japanese government publications.
Author & Citation

**Tshewang Gyeltshen**   
Graduate Program in Global Health Policy (GHP),   
Graduate School of Medicine (GSM), The University of Tokyo   

If you use this dataset or code, please cite the `popjp` package rather than
this repository:   
**Gyeltshen T (2026). popjp: Prefecture-Level Population of Japan, 1970-2024.
R package version 0.1.0. https://doi.org/10.5281/zenodo.21830077**

**License**   
This repository contains only derived products from public-use official government data.
Processed data and code are released under the MIT License.
Users must cite e-Stat as the original source of government statistics.
