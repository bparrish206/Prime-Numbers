B-s-test-code
=============
#Global list of the first 11 prime numbers
prime11 = (2,  3,  5,  7,  11,  13,  17,  19,  23,  29,  31)

#main function that asks users for number from 1 to 1000 and displays then prime factors
def main():
    #get user input
    num = int(input('Enter a positive integer between 1 and 1,000:'))
    #call factor function to get and return prime factors
    factors(num)
    
    #Test cases
    factors(2500)
    factors(-50)
    factors(12)
    factors(60)
    factors(217)
    factors(862)
    factors(133)
    factors(253)

#factor finder function
def factors(num):
    #variable to store user number chosen
    n = num
    #create a list for the prime factors to go
    ftrs = []
    #validate input
    if n <=1000 and n >=1:
        #loop through primes
        for i in prime11:
            # if one of them works
            while n % i == 0:
                #add it to list
                ftrs.append(i)
                #divide value and loop again
                n = int(n/i)
        #when value will no longer divide
        if n % i != 0:
            if n != 1:
                #add it factor list
                ftrs.append(n)
            else:
                 pass
        #clean the factor list up
        ftrs.sort()
        #print it out
        print(' The factors of %d:' % num, str(ftrs)[1:-1], '\n')
    #if bad data tell user
    else:
        print('Integer must be between 1 and 1,000.', '\n')
    
#call main
main()
