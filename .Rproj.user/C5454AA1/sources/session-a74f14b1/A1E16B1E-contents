# Make conjoint surveys using the cbcTools package

# Install packages
# install.packages("remotes")
# install.packages("tidyverse")
# remotes::install_github("jhelvy/cbcTools")

# Load libraries
library(cbcTools)
library(tidyverse)

# Define profiles with attributes and levels
profiles <- cbc_profiles(
     shape     = c('Patch','Wristband','Ring'),
     price     = seq(50, 400, 50), 
     battery = seq(1,7,0.5)
)

# Make a basic survey using the full factorial of all profiles
design <- cbc_design(
    profiles = profiles,
    n_resp   = 2000, # Number of respondents
    n_alts   = 3,    # Number of alternatives per question
    n_q      = 8     # Number of questions per respondent
)

head(design) # preview

# Add image names matched to the apple type
# (we'll use these to display images in the survey)
image_names <- data.frame(
    type = c('Patch', 'Main', 'Wrist'),
    image = c('patch.jpg', 'ring.jpg', 'wrist.jpg')
)
#design <- design %>%
    #left_join(image_names, by = "type")
#head(design) # preview

# Save design
design <- write_csv(design, 'choice_questions.csv')


