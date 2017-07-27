- tally (mosaic)
- head, tail (base)
- summary (base)
- names (base)
- arrange (dplyr)
- favstats (mosaic)
- sort (base)
- %>% (dplyr)
- subset (base), filter (dplyr)
- tally(~state, data=counties) %>% sort()
- median et al from mosaic (  median(~pop2010|state, data=counties)  )
- View (rstudio)
- pdist, xpnorm, xqnorm, xpbinom (mosaic)


# Plotting

- histogram (lattice)
- bargraph (mosaic)
- mosaicplot (mosaic)
- xyplot (lattice)
- ladd (mosaic)
- panel.abline (lattice)
- ...


# Example commands

counties %>% mutate(per_capita_spending=fed_spending/pop2010) %>% filter(!is.na(per_capita_spending)) %>% arrange(per_capita_spending) %>% tail(10)

