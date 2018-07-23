# Guided project: U.S. Births

# Read the birth dataset as a string, then as a list of lists

f = open('births.csv', 'r')
string_text = f.read()
print(string_text)
cleaner_text = string_text.split('\n')
print(cleaner_text)

# Create a dictionary showing the number of births per day of the week

days_count = {}
data = cleaner_text[1:]
for each in data:
    splitted_line = each.split(',')
    day_of_week = splitted_line[3]
    births = int(splitted_line[4])
    if day_of_week in days_count:
        days_count[day_of_week] += births
    else:
        days_count[day_of_week] = births
print(days_count)
