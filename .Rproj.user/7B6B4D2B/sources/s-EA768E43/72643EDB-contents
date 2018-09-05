library("tidyverse")
str(surveys)

select(surveys,species_id,weight)
filter(surveys,year==1995)
# Pipes %>% 
surveys %>% 
filter(year==1995) %>% 
  select (species_id,weight)

select (species_id,weight)
exercise <- surveys %>% 
filter(weight<5) %>% 
select (species_id,weight,sex)
#create new column
#mutate()
data_with_kg <- surveys %>% 
 surveys %>%
  mutate(weight_kg=weight/1000,weight_kg2=weight*2)   

surveys %>%
 mutate(weight_kg=weight/1000,weight_kg2=weight_kg*2) %>% 
 head()
surveys %>% 
  filter(!is.na(weight)) %>% 
  mutate(weight_kg=weight/1000,weight_kg2=weight_kg*2) %>% 
  head()
#remove the missing values first (using filter), and re-run 
surveys %>%
  group_by(sex) %>% 
  summarise(mean_weight=mean(weight,na.rm = TRUE))
#Using the previous command
#remove the missing values first (using filter), and re-run

#group by two columns

summarise_two <- surveys %>%
   filter(!sex=="") %>% 
   filter(!is.na(weight)) %>% 
  group_by(sex,species_id) %>% 
  summarise(mean_weight=mean(weight))

#summarise the previous commands add a new column that gives the 
#minimum weight and maximum weight

summarise_minweight <- surveys %>%
  filter(!sex=="") %>% 
  filter(!is.na(weight)) %>% 
  group_by(sex,species_id) %>% 
  summarise(mean_weight=mean(weight,na.rm=TRUE),min_weight=min(weight),max_weight=max(weight))

#counting with two variables

surveys %>% 
  filter(!sex=="") %>% 
  count(sex,species)

#sorting arrange()

surveys %>% 
  filter(!sex=="") %>% 
  count(sex,species) %>% 
  arrange(species,desc(n))

# Species id only female

surveys %>% 
  filter(!sex=="F") %>% 
  count(species) %>% 
  arrange(species,desc(n))

          