##################
# MHI 289 - Python
# Aldreen Venzon
# 1.10.19
# Loan repayment Calculator Extra Credit 1.py
##################

#Data input
pv = int(input('How much is being borrowed (no commas)? ')) #principal
ry = float(input('What is the annual interest rate (enter it without the % sign)? ')) #interest rate in years
r = (ry/100)/12
ny = int(input('How many years is the loan for? ')) #number of years
n = ny * 12 #number of months

P = r * pv/(1-(1+r)**(-n)) #payment per month

#Print out results and labels
print("Payment schedule for a loan of $", pv, " at", ry, "% interest, repaid over ", ny, "year(s): ")
print("month ", "payment ", "principal", "interest", "total int", "remaining ")

#While there are still payments left, print each month's results
m = 1 #start all variables and counter at 1st month
interest = r * pv
total_int = interest
principle = P - interest
    
while m <= n: #increment all variable to n month
    RP = pv*(1-(1+r)**(m-n)) / (1-(1+r)**(-n)) #remaining payment per month
    
    print(" %3d %8.2f %8.2f %8.2f %8.2f %12.2f" % (m, P, principle, interest, total_int, RP)) #print in table format   
   
    interest = r * RP #remaining payment per month
    total_int += interest #add to total 
    principle = P - interest #subtract interest to principal
    
    m += 1 #increment by 1 month
