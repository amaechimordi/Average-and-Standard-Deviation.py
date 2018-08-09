#Mordi Amaechi
#CptS 111, Spring 2018
#Programming Assignment #5
#March 20, 2018
#A Statistics Program
#This program takes a list of floats and calculates the average and standard deviation of the list

def main():
    '''This calls all the fucntions in the program'''
    num_list = int(input('Enter the number of list elements:')) #asks the user to input the number of items he wants in the list
    float_nums = get_floats(num_list)
    sum_hard = summer(float_nums)
    avgr = average(float_nums)
    stan_dev1 = std_dev(float_nums, avgr)


def get_floats(num_list):
    '''Creates a list of floats the user inputs depending on the number of items wanted in the list'''
    float_nums = [] #an empty list accumulator
    for num1 in range(num_list): #loops as many times depending on what the user inputs and asks for a float input each time
        floats1 = float(input('Enter float %d:' %(num1 + 1))) #prompts the user for the float values he or she wants in the list 
        float_nums.append(floats1) #adds the users input to the empty list
    return float_nums


def summer(float_nums):
    '''This function sums up the list'''
    sum_hard = 0 #an accumulator to 0
    for num2 in float_nums: #this loops over each value in the list
        sum_hard += num2 #and adds it to the lvalue sum_hard
    return sum_hard


def average(float_nums):
    '''This function gives you the average of a list'''
    avgr = summer(float_nums) / len(float_nums) #calculates the average by calling the summer() function and dividing it by the length of the list
    print('Average', '=', avgr) #prints the average
    return avgr


def std_dev(float_nums, avgr):
    '''This function give you the standard deviation of a list'''
    stan_dev1 = 0
    for vari in float_nums: #loops over the float list which the user input
       stan_dev2 = (vari - avgr) ** 2 #this partially calculates the variance
       stan_dev1 += stan_dev2 #adds the values fromt the list to obtain the standard deviation
    stan_dev1 = (stan_dev1 / len(float_nums)) ** 0.5 #this calculates the variance plus the standard deviation
    print('Standard deviation', '=', round(stan_dev1, 2)) #prints the standard deviation and rounds it to 2 decimal places
    return stan_dev1
    

main()

