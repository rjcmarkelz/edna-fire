# Owners - Anna Holmquist
# license
# edna fire project directory

## /scripts
directory for analysis scripts go here

# /data
directory small datasets go here

# /output
directory to save intermediary files and output

# /figures
directory for figure drafts and final figures


##################
# Docker Pipeline
###################

Download base container.
```bash
docker pull quay.io/biocontainers/bioconductor-dada2:1.22.0--r41h619a076_1
docker run -it quay.io/biocontainers/bioconductor-dada2:1.22.0--r41h619a076_1 /bin/bash
```
# inside biocontainer start an R session

```R
install.packages("tidyverse")
install.packages("stringr")
sessionInfo(package = NULL)

# R version 4.1.2 (2021-11-01)
# Platform: x86_64-conda-linux-gnu (64-bit)
# Running under: Debian GNU/Linux 10 (buster)
#
# Matrix products: default
# BLAS/LAPACK: /usr/local/lib/libopenblasp-r0.3.18.so
#
# locale:
#  [1] LC_CTYPE=C.UTF-8       LC_NUMERIC=C           LC_TIME=C.UTF-8
#  [4] LC_COLLATE=C.UTF-8     LC_MONETARY=C.UTF-8    LC_MESSAGES=C.UTF-8
#  [7] LC_PAPER=C.UTF-8       LC_NAME=C              LC_ADDRESS=C
# [10] LC_TELEPHONE=C         LC_MEASUREMENT=C.UTF-8 LC_IDENTIFICATION=C
#
# attached base packages:
# [1] stats     graphics  grDevices utils     datasets  methods   base
#
# other attached packages:
# [1] forcats_0.5.2   stringr_1.4.1   dplyr_1.0.9     purrr_0.3.4
# [5] readr_2.1.2     tidyr_1.2.0     tibble_3.1.6    ggplot2_3.3.5
# [9] tidyverse_1.3.2
#
# loaded via a namespace (and not attached):
#  [1] pillar_1.7.0        compiler_4.1.2      cellranger_1.1.0
#  [4] dbplyr_2.2.1        tools_4.1.2         lubridate_1.8.0
#  [7] jsonlite_1.8.0      googledrive_2.0.0   lifecycle_1.0.1
# [10] gargle_1.2.0        gtable_0.3.0        pkgconfig_2.0.3
# [13] rlang_1.0.4         reprex_2.0.2        DBI_1.1.3
# [16] cli_3.3.0           haven_2.5.1         xml2_1.3.3
# [19] withr_2.4.3         httr_1.4.4          generics_0.1.3
# [22] vctrs_0.4.1         fs_1.5.2            hms_1.1.2
# [25] googlesheets4_1.0.1 grid_4.1.2          tidyselect_1.1.2
# [28] glue_1.6.2          R6_2.5.1            fansi_1.0.2
# [31] readxl_1.4.1        tzdb_0.3.0          modelr_0.1.9
# [34] magrittr_2.0.2      backports_1.4.1     scales_1.1.1
# [37] ellipsis_0.3.2      rvest_1.0.3         assertthat_0.2.1
# [40] colorspace_2.0-3    utf8_1.2.2          stringi_1.7.6
# [43] munsell_0.5.0       broom_1.0.0         crayon_1.5.0
```

Outside of container.
```bash
docker commit intelligent_feistel biocontainers_dada2_tidyverse
docker images biocontainers_dada2_tidyverse
# REPOSITORY                      TAG       IMAGE ID       CREATED         SIZE
# biocontainers_dada2_tidyverse   latest    c1f8a711f890   6 minutes ago   1.18GB
```

Download base container.
```bash
docker pull quay.io/biocontainers/bioconductor-dada2:1.22.0--r41h619a076_1
docker run -it quay.io/biocontainers/bioconductor-dada2:1.22.0--r41h619a076_1 /bin/bash
```


Download base container.
```bash
docker pull rocker/tidyverse
docker run -it rocker/tidyverse /bin/bash
```
# inside container start an R session

```R
install.packages("ape")
install.packages("vegan")
install.packages("BAT")
sessionInfo(package = NULL)

# R version 4.2.1 (2022-06-23)
# Platform: x86_64-pc-linux-gnu (64-bit)
# Running under: Ubuntu 20.04.4 LTS
#
# Matrix products: default
# BLAS:   /usr/lib/x86_64-linux-gnu/openblas-pthread/libblas.so.3
# LAPACK: /usr/lib/x86_64-linux-gnu/openblas-pthread/liblapack.so.3
#
# locale:
#  [1] LC_CTYPE=en_US.UTF-8       LC_NUMERIC=C
#  [3] LC_TIME=en_US.UTF-8        LC_COLLATE=en_US.UTF-8
#  [5] LC_MONETARY=en_US.UTF-8    LC_MESSAGES=en_US.UTF-8
#  [7] LC_PAPER=en_US.UTF-8       LC_NAME=C
#  [9] LC_ADDRESS=C               LC_TELEPHONE=C
# [11] LC_MEASUREMENT=en_US.UTF-8 LC_IDENTIFICATION=C
#
# attached base packages:
# [1] stats     graphics  grDevices utils     datasets  methods   base
#
# loaded via a namespace (and not attached):
# [1] compiler_4.2.1 tools_4.2.1


```

Outside of container.
```bash
docker commit trusting_wilson rocker_tidyverse_ape_vegan_bat
docker images
# REPOSITORY                                 TAG                     IMAGE ID       CREATED          SIZE
# rocker_tidyverse_ape_vegan_bat             latest                  afd3d3390eb3   31 seconds ago   2.46GB
```
