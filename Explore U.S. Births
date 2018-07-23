def read_csv(file):
    """ (csv) -> list of lists
    Open file, take away the header, and return the file content
    as a list of lists, all with integer values.
    """

    f = open(file)
    string_data = f.read()
    rows = string_data.split('\n')
    string_list = rows[1:]
    final_list = []
    for row in string_list:
        int_fields = []
        string_fields = row.split(',')
        for elem in string_fields:
            int_fields.append(int(elem))
        final_list.append(int_fields)
    return final_list

# Read the cdc data using the new function

cdc_list = read_csv('US_births_1994-2003_CDC_NCHS.csv')
cdc_list[:10]

def calc_counts(data, column):
    """ (list) -> dictionary
    Return a dictionary with the number of births per column
    in data.
    """

    births_per_parameter = {}
    for elem in data:
        parameter = elem[column]
        births = elem[4]
        if parameter in births_per_parameter:
            births_per_parameter[parameter] += births
        else:
            births_per_parameter[parameter] = births
    return births_per_parameter

# Number of births per year

cdc_year_births = calc_counts(cdc_list, 0)
cdc_year_births

# Number of births per month

cdc_month_births = calc_counts(cdc_list, 1)
cdc_month_births

# Number of births per day of the month

cdc_dom_births = calc_counts(cdc_list, 2)
cdc_dom_births

# Number of births per day of the week

cdc_dow_births = calc_counts(cdc_list, 3)
cdc_dow_births

def dict_extremes(d):
    """ (dict) -> tuple
    Return the min and the max value of d.
    """
    lst = []
    for key in d:
        lst.append(key)

    max_dict = d[lst[0]]
    for key in d:
        if d[key] > max_dict:
            max_dict = d[key]

    min_dict = d[lst[0]]
    for key in d:
        if d[key] < min_dict:
            min_dict = d[key]
    return min_dict, max_dict

# Minimum and maximum number of births per day of the week

min_max_dow_births = dict_extremes(cdc_dow_births)
min_max_dow_births

# Read the ssa data
ssa_list = read_csv('US_births_2000-2014_SSA.csv')

# One way of combining the two datasets

 ssa_2004andup = []
for lst in ssa_list:
    if lst[0] > 2003:
        ssa_2004andup.append(lst)

cdc_list.append(ssa_2004andup)
print(cdc_list)
