# Machine_Learning_I
Github repo for all of the Machine Learning Projects

# races.csv
Each line describes the condition of an individual race.

race_id - unique identifier for the race

date - date of the race, in YYYY-MM-DD format (note that the dates given have been obscured and are not the real ones, although the durations between each race should be correct)

venue - a 2-character string, representing which of the 2 race courses this race took place at: ST = Shatin, HV = Happy Valley

race_no - race number of the race in the day's meeting

config - race track configuration, mostly related to the position of the inside rail. For more details, see the HKJC website.

surface - a number representing the type of race track surface: 1 = dirt, 0 = turf

distance - distance of the race, in metres

going - track condition. For more details, see the HKJC website.

horse_ratings - the range of horse ratings that may participate in this race

prize - the winning prize, in HK Dollars

race_class - a number representing the class of the race

sec_time1 - time taken by the leader of the race to reach the end of the end of the 1st sectional point (sec)

sec_time2 - time taken by the leader of the race to reach the end of the 2nd sectional point (sec)

sec_time3 - time taken by the leader of the race to reach the end of the 3rd sectional point (sec)

sec_time4 - time taken by the leader of the race to reach the end of the 4th sectional point, if any (sec)

sec_time5 - time taken by the leader of the race to reach the end of the 5th sectional point, if any (sec)

sec_time6 - time taken by the leader of the race to reach the end of the fourth sectional point, if any (sec)

sec_time7 - time taken by the leader of the race to reach the end of the fourth sectional point, if any (sec)

time1 - time taken by the leader of the race in the 1st section only (sec)

time2 - time taken by the leader of the race in the 2nd section only (sec)

time3 - time taken by the leader of the race in the 3rd section only (sec)

time4 - time taken by the leader of the race in the 4th section only, if any (sec)

time5 - time taken by the leader of the race in the 5th section only, if any (sec)

time6 - time taken by the leader of the race in the 6th section only, if any (sec)

time7 - time taken by the leader of the race in the 7th section only, if any (sec)

place_combination1 - placing horse no (1st)

place_combination2 - placing horse no (2nd)

place_combination3 - placing horse no (3rd)

place_combination4 - placing horse no (4th)

placedividend1 - placing dividend paid (for placecombination1)

placedividend2 - placing dividend paid (for placecombination2)

placedividend3 - placing dividend paid (for placecombination2)

placedividend4 - placing dividend paid (for placecombination2)

win_combination1 - winning horse no

windividend1 - winning dividend paid (for wincombination1)

win_combination2 - joint winning horse no, if any

windividend2 - winning dividend paid (for wincombination2, if any)

# runs.csv
Each line describes the characteristics of one horse run, in one of the races given in races.csv.

race_id - unique identifier for the race

horse_no - the number assigned to this horse, in the race

horse_id - unique identifier for this horse

result - finishing position of this horse in the race

won - whether horse won (1) or otherwise (0)

lengths_behind - finishing position, as the number of horse lengths behind the winner

horse_age - current age of this horse at the time of the race

horse_country - country of origin of this horse

horse_type - sex of the horse, e.g. 'Gelding', 'Mare', 'Horse', 'Rig', 'Colt', 'Filly'

horse_rating - rating number assigned by HKJC to this horse at the time of the race

horse_gear - string representing the gear carried by the horse in the race. An explanation of the codes used may be found on the HKJC website.

declared_weight - declared weight of the horse and jockey, in lbs

actual_weight - actual weight carried by the horse, in lbs

draw - post position number of the horse in this race

position_sec1 - position of this horse (ranking) in section 1 of the race

position_sec2 - position of this horse (ranking) in section 2 of the race

position_sec3 - position of this horse (ranking) in section 3 of the race

position_sec4 - position of this horse (ranking) in section 4 of the race, if any

position_sec5 - position of this horse (ranking) in section 5 of the race, if any

position_sec6 - position of this horse (ranking) in section 6 of the race, if any

behind_sec1 - position of this horse (lengths behind leader) in section 1 of the race

behind_sec2 - position of this horse (lengths behind leader) in section 2 of the race

behind_sec3 - position of this horse (lengths behind leader) in section 3 of the race

behind_sec4 - position of this horse (lengths behind leader) in section 4 of the race, if any

behind_sec5 - position of this horse (lengths behind leader) in section 5 of the race, if any

behind_sec6 - position of this horse (lengths behind leader) in section 6 of the race, if any

time1 - time taken by the horse to pass through the 1st section of the race (sec)

time2 - time taken by the horse to pass through the 2nd section of the race (sec)

time3 - time taken by the horse to pass through the 3rd section of the race (sec)

time4 - time taken by the horse to pass through the 4th section of the race, if any (sec)

time5 - time taken by the horse to pass through the 5th section of the race, if any (sec)

time6 - time taken by the horse to pass through the 6th section of the race, if any (sec)

finish_time - finishing time of the horse in this race (sec)

win_odds - win odds for this horse at start of race

place_odds - place (finishing in 1st, 2nd or 3rd position) odds for this horse at start of race

trainer_id - unique identifier of the horse's trainer at the time of the race

jockey_id - unique identifier of the jockey riding the horse in this race

# Source:
https://www.kaggle.com/gdaley/hkracing?select=runs.csv
