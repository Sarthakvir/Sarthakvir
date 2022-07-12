# Read the three input lists, i.e. 'C', 'F', and 'H'.
input_list_c = [2, 5, 9, 12, 13, 15, 16, 17, 18, 19]
input_list_f = [2, 4, 5, 6, 7, 9, 13, 16, 20]
input_list_h = [1, 2, 5, 9, 10, 11, 12, 13, 15, 20]

mc = max(input_list_c)
mf = max(input_list_f)
mh = max(input_list_h)
#if condition to show max of input of cricket is more than football and football is more than hockey.
if mc > mf & mc > mh:
    m = mc
elif mf > mc & mf > mh:
    m = mf
else:
    m = mh

nc = min(input_list_c)
nf = min(input_list_f)
nh = min(input_list_h)

if nc < nf & nc < nh:
    n = nc
elif nf < nc & nf > nh:
    n = nf
else:
    n = nh
# Convert the given lists to sets as it is easier to perform the given operations
# on sets
# The following opeartion gives the students who play only Cricket and Football.
# Note that only (C & F) also contains the students who play all the three sports
# and hence, we need to subtract (C & F & H) from it.
C = set(input_list_c)
F = set(input_list_f)
H = set(input_list_h)
A = set(range(n,m))
Y = (C&F&H)
# Perform an '&' operation between the three sets to find out the students who play
# all the three sports. Finally, convert it into a list, apply the sorted() function
# and print the resultant list.
print(sorted(list(Y)))
print(sorted(list((C&F)-H)))
print(sorted(list((C&F|C&H|F&H)-Y)))
print(sorted(list(A-(C|F|H))))
