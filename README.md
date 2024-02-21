# R_tidyr_cheatsheet

## Installation : 

```R
# Tidyr Package Cheatsheet

## Installing the package
```R
install.packages("tidyr")
library(tidyr)
```
## Basics Functions : 

### billboard

* `billboard`	- Song rankings for Billboard top 100 in the year 2000

```R
library(tidyverse)

billboard_data <- tibble(
  song = c("Song1", "Song2", "Song3"),
  rank = c(1, 2, 3)
)
```

### Chop and Unchop

* `chop`	- hopping and unchopping preserve the width of a data frame, changing its length. `chop()` makes `df` shorter by converting rows within each group into list-columns. 

```R
chopped_data <- chop(billboard_data)
unchopped_data <- unchop(chopped_data)
```

### cms_patient_care

* `cms_patient_care`	- Data from the Centers for Medicare & Medicaid Services

```R
cms_patient_care_data <- cms_patient_care
```

### cms_patient_experience

* `cms_patient_experience` -	Data from the Centers for Medicare & Medicaid Services

```R
cms_patient_experience_data <- cms_patient_experience
```

### complete
* `complete` -	Complete a data frame with missing combinations of data
```R
complete_data <- complete(billboard_data, song = c("Song1", "Song2", "Song3"))
```

### construction
* `construction` -	Completed construction in the US in 2018
```R
construction_data <- construction
```

### crossing
* `crossing`	- Expand data frame to include all possible combinations of values
```R
crossing_data <- crossing(x = c("A", "B"), y = c(1, 2))
```

### drop_na
* `drop_na`	- Drop rows containing missing values

```R
data_without_na <- drop_na(billboard_data)
```

### expand
* `expand`	- Expand data frame to include all possible combinations of values
```R
expanded_data <- expand(billboard_data, song = c("Song1", "Song2", "Song3"), rank = 1:3)
```

### expand_grid
* `expand_grid`	-Create a tibble from all combinations of inputs
```R
expanded_grid_data <- expand_grid(song = c("Song1", "Song2", "Song3"), rank = 1:3)
```

### extract
* `extract`	- Extract a character column into multiple columns using regular expression groups
```R
extracted_data <- extract(billboard_data, song, into = c("artist", "title"), regex = "(.*) - (.*)")
```

### fill
* `fill`	- Fill in missing values with previous or next value
```R
filled_data <- fill(billboard_data, rank)
```

### fish_encounters
* `fish_encounters`-	Fish encounters

```R
fish_encounters_data <- fish_encounters
```

### full_seq
* `full_seq` -	Create the full sequence of values in a vector

```R
full_sequence <- full_seq(1:5, period = 2)
```

### gather
* `gather`	 - Gather columns into key-value pairs

```R
gathered_data <- gather(billboard_data, key = "attribute", value = "value", -song)
```

### hoist
* `hoist`	- Hoist values out of list-columns
```R
hoisted_data <- hoist(tibble(x = list(1, 2, 3)))
```

### household
* `household`	 - Household data
```R
household_data <- household
```

### nest
* `nest`	- Nest rows into a list-column of data frames
```R
nested_data <- nest(billboard_data, data = -song)
```

### nesting
* `nesting`	- Expand data frame to include all possible combinations of values

```R
nested_data_expanded <- nesting(billboard_data, song = c("Song1", "Song2", "Song3"), rank = 1:3)
```

### nest_legacy
* `nest_legacy`	- Legacy versions of 'nest()' and 'unnest()'
```R
nested_data_legacy <- nest_legacy(billboard_data, data = -song)
```

### pack
* `pack`	- Pack and unpack
```R
packed_data <- pack(billboard_data)
unpacked_data <- unpack(packed_data)

```

### pivot_longer
* `pivot_longer`	- Pivot data from wide to long
```R
longer_data <- pivot_longer(billboard_data, cols = rank, names_to = "position", values_to = "rank")
```

### pivot_wider
* `pivot_wider`	- Pivot data from long to wide
```R
wider_data <- pivot_wider(longer_data, names_from = "position", values_from = "rank")
```

### population
* `population`	- World Health Organization TB data
```R
population_data <- population
```

### relig_income
* `relig_income`- 	Pew religion and income survey
```R
relig_income_data <- relig_income
```

### replace_na
* `replace_na`	- Replace NAs with specified values
```R
data_with_replaced_na <- replace_na(billboard_data, list(rank = 0))
```

### separate
* `separate`	- Separate a character column into multiple columns with a regular expression or numeric locations.

```R
separated_data <- separate(billboard_data, col = song, into = c("artist", "title"), sep = " - ")
```

### separate_longer_delim
* `separate_longer_delim`	- Split a string into rows

```R
separated_longer_data <- separate_longer_delim(billboard_data, col = song, sep = ",")
```

### separate_longer_position
* `separate_longer_position`	- Split a string into rows

```R
separated_longer_data <- separate_longer_position(billboard_data, col = song, sep = c(1, 3))
```

### separate_rows
* `separate_rows`- 	Separate a collapsed column into multiple rows
```R
separated_rows_data <- separate_rows(billboard_data, col = song, sep = ",")
```

### separate_wider_delim
* `separate_wider_delim`	- Split a string into columns
```R
separated_wider_data <- separate_wider_delim(billboard_data, col = song, sep = ",")
```

### separate_wider_position
* `separate_wider_position`	- Split a string into columns
```R
separated_wider_data <- separate_wider_position(billboard_data, col = song, sep = c(1, 3))
```

### separate_wider_regex
* `separate_wider_regex`	- Split a string into columns
```R
separated_wider_data <- separate_wider_regex(billboard_data, col = song, regex = "(.*) - (.*)")
```

### smiths
* `smiths`	- Some data about the Smith family
```R
smiths_data <- smiths
```

### spread
* `spread`	- Spread a key-value pair across multiple columns
```R
spread_data <- spread(gathered_data, key = "attribute", value = "value")
```
### table1
* `table1`	- Example tabular representations
```R
table1_data <- table1
```
### table2
* `table2`	- Example tabular representations
```R
table2_data <- table2
```
### table3
* `table3`	- Example tabular representations

```R
table3_data <- table3
```
### table4a
* `table4a`	- Example tabular representations
```R
table4a_data <- table4a
```
### table4b
* `table4b`	- Example tabular representations
```R
table4b_data <- table4b
```

### table5
* `table5`	- Example tabular representations
```R
table5_data <- table5
```

### uncount
* `uncount`	- "Uncount" a data frame

```R
uncounted_data <- uncount(billboard_data, wt = rank)
```
### unite
* `unite`	- Unite multiple columns into one by pasting strings together
```R
united_data <- unite(billboard_data, col = "combined", song, rank, sep = " - ")
```
### unnest
* `unnest`	- a list-column of data frames into rows and columns
```R
unnested_data <- unnest(nested_data)
```
### unnest_legacy
* `unnest_legacs`  - 	Legacy versions of 'nest()' and 'unnest()'
```R
unnested_data_legacy <- unnest_legacy(nested_data_legacy)
```

### unnest_longer
* `unnest_longer`	- Unnest a list-column into rows

```R
unnested_longer_data <- unnest_longer(nested_data)
```

### unnest_wider
* `unnest_wider`	- Unnest a list-column into columns
```R
unnested_wider_data <- unnest_wider(nested_data)
```

### unpack
* `unpack`	- Pack and unpack
```R
packed_data <- pack(billboard_data)
unpacked_data <- unpack(packed_data)
```
### us_rent_income
* `us_rent_income`	- US rent and income data
```R
us_rent_income_data <- us_rent_income
```

### who
* `who`	- World Health Organization TB data
```R
who_data <- who
```

### who2
* `who2`	- World Health Organization TB data
```R
who2_data <- who2
```

### world_bank_pop
* `world_bank_pop`	- Population data from the World Bank
```R
world_bank_pop_data <- world_bank_pop
```

