# Owners - Anna Holmquist
# license
# edna fire project directory

## /scripts

To run the following scripts:
dada2_bf3.Rmd
dada2_mco.Rmd

Change the path to match your directory path for where the data is located.
```bash
docker run -it -v /Users/rjcmarkelz/Documents/Projects/THINK/git.repos/BIDS/DATA/Fire_Raw:/DATA/ biocontainers_dada2_tidyverse /bin/bash
```

To run the following scripts:
fire_cleanup.Rmd

Change the path to match your directory path for where the data is located.
```bash
docker run -it -v /Users/rjcmarkelz/Documents/Projects/THINK/git.repos/BIDS/DATA/Fire_Raw:/DATA/ rocker_geospatial_tidyverse_ape_vegan_bat_lulu /bin/bash
```

To run the following scripts:
fire_analysis.Rmd

Change the path to match your directory path for where the data is located.
```bash
docker run -it -v /Users/rjcmarkelz/Documents/Projects/THINK/git.repos/BIDS/DATA/Fire_Raw:/DATA/ rocker_geospatial_tidyverse_ape_vegan_bat_lulu /bin/bash
```


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

docker run -it rocker/geospatial /bin/bash


```
# inside container start an R session

```R
install.packages("BAT", dependencies = TRUE)
install.packages("ape")
install.packages("vegan")
install.packages("BiocManager")
# BiocManager::install(version = "3.14")
install.packages("devtools")
devtools::install_github("tobiasgf/lulu")  

# load the packages to make sure they are working
library(BAT)
library(lulu)
library(ape)
library(vegan)
library(tidyverse)

sessionInfo(package = NULL)
# R version 4.1.1 (2021-08-10)
# Platform: x86_64-pc-linux-gnu (64-bit)
# Running under: Ubuntu 20.04.3 LTS
#
# Matrix products: default
# BLAS/LAPACK: /usr/lib/x86_64-linux-gnu/openblas-pthread/libopenblasp-r0.3.8.so
#
# locale:
#  [1] LC_CTYPE=en_US.UTF-8       LC_NUMERIC=C
#  [3] LC_TIME=en_US.UTF-8        LC_COLLATE=en_US.UTF-8
#  [5] LC_MONETARY=en_US.UTF-8    LC_MESSAGES=C
#  [7] LC_PAPER=en_US.UTF-8       LC_NAME=C
#  [9] LC_ADDRESS=C               LC_TELEPHONE=C
# [11] LC_MEASUREMENT=en_US.UTF-8 LC_IDENTIFICATION=C
#
# attached base packages:
# [1] stats     graphics  grDevices utils     datasets  methods   base
#
# other attached packages:
#  [1] forcats_0.5.1   stringr_1.4.0   dplyr_1.0.7     purrr_0.3.4
#  [5] readr_2.0.1     tidyr_1.1.3     tibble_3.1.8    ggplot2_3.3.5
#  [9] tidyverse_1.3.1 vegan_2.6-2     lattice_0.20-44 permute_0.9-7
# [13] ape_5.6-2       lulu_0.1.0      BAT_2.9.0
#
# loaded via a namespace (and not attached):
#   [1] readxl_1.3.1         backports_1.2.1      plyr_1.8.6
#   [4] sp_1.4-5             splines_4.1.1        listenv_0.8.0
#   [7] usethis_2.1.6        digest_0.6.27        foreach_1.5.2
#  [10] htmltools_0.5.2      fansi_0.5.0          magrittr_2.0.1
#  [13] memoise_2.0.1        cluster_2.1.2        doParallel_1.0.17
#  [16] ks_1.13.5            tzdb_0.1.2           remotes_2.4.2
#  [19] recipes_1.0.1        globals_0.14.0       fastcluster_1.2.3
#  [22] modelr_0.1.8         gower_1.0.0          hardhat_1.2.0
#  [25] pdist_1.2.1          prettyunits_1.1.1    colorspace_2.0-2
#  [28] rvest_1.0.1          haven_2.4.3          callr_3.7.0
#  [31] crayon_1.4.1         jsonlite_1.7.2       survival_3.2-11
#  [34] iterators_1.0.14     glue_1.6.2           gtable_0.3.0
#  [37] ipred_0.9-13         pkgbuild_1.3.1       future.apply_1.9.0
#  [40] maps_3.3.0           abind_1.4-5          scales_1.1.1
#  [43] mvtnorm_1.1-3        DBI_1.1.1            miniUI_0.1.1.1
#  [46] Rcpp_1.0.7           xtable_1.8-4         progress_1.2.2
#  [49] palmerpenguins_0.1.1 magic_1.5-9          proxy_0.4-26
#  [52] mclust_5.4.10        stats4_4.1.1         lava_1.6.10
#  [55] prodlim_2019.11.13   profvis_0.3.7        htmlwidgets_1.5.3
#  [58] httr_1.4.2           ellipsis_0.3.2       urlchecker_1.0.1
#  [61] pkgconfig_2.0.3      nnet_7.3-16          dbplyr_2.1.1
#  [64] utf8_1.2.2           caret_6.0-93         tidyselect_1.1.2
#  [67] rlang_1.0.4          reshape2_1.4.4       later_1.3.0
#  [70] cellranger_1.1.0     munsell_0.5.0        tools_4.1.1
#  [73] cachem_1.0.6         cli_3.3.0            generics_0.1.3
#  [76] devtools_2.4.4       broom_0.7.9          geometry_0.4.5
#  [79] fastmap_1.1.0        ModelMetrics_1.2.2.2 processx_3.5.2
#  [82] fs_1.5.2             future_1.22.1        nlme_3.1-152
#  [85] mime_0.11            xml2_1.3.2           pracma_2.3.8
#  [88] compiler_4.1.1       rstudioapi_0.13      curl_4.3.2
#  [91] e1071_1.7-8          reprex_2.0.1         stringi_1.7.4
#  [94] ps_1.6.0             rgeos_0.5-5          Matrix_1.3-4
#  [97] vctrs_0.4.1          pillar_1.8.1         lifecycle_1.0.1
# [100] data.table_1.14.0    raster_3.4-13        httpuv_1.6.2
# [103] R6_2.5.1             promises_1.2.0.1     KernSmooth_2.23-20
# [106] parallelly_1.27.0    sessioninfo_1.2.2    codetools_0.2-18
# [109] MASS_7.3-54          assertthat_0.2.1     pkgload_1.3.0
# [112] proto_1.0.0          rprojroot_2.0.2      withr_2.5.0
# [115] mgcv_1.8-36          parallel_4.1.1       hms_1.1.0
# [118] terra_1.3-22         grid_4.1.1           rpart_4.1-15
# [121] timeDate_4021.104    class_7.3-19         nls2_0.3-3
# [124] hypervolume_3.0.4    pROC_1.18.0          shiny_1.6.0
# [127] lubridate_1.8.0

citation("BAT")
citation("lulu")
citation("ape")
citation("vegan")
citation("tidyverse")

```

Outside of container.
```bash
# get the nickname of the running container with the newly installed packages
docker ps
docker commit amazing_kepler rocker_geospatial_tidyverse_ape_vegan_bat_lulu
docker images
# REPOSITORY                                       TAG                     IMAGE ID       CREATED          SIZE
# rocker_geospatial_tidyverse_ape_vegan_bat_lulu   latest                  c51e0fa4391c   29 seconds ago   5.15GB
```

Download base container.
```bash
docker pull ncbi/blast

docker run -it -v /Users/rjcmarkelz/Documents/Projects/THINK/git.repos/BIDS/DATA/Fire_Raw:/DATA/ ncbi/blast /bin/bash
```
