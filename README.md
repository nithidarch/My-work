# My-work
This is part of my work
def Fitness(x):
    global weight, balance, swingWeight, Length
    global tW, tI, mgRI;
    global fit
    
    w = weight
    bl = balance
    sw = swingWeight
    lg = Length
    
    if fitfunc == 1:
        n = len(x)
        for i in range(n):
            if i == n-1 and (Length == 27.5 or Length == 28.5):
                ii = Length
            else:
                ii = i
            weight1 = w+x[i]
            r = (lg/2.0) - (bl*0.125)
            R1 = ((w*r)+(x[i]*ii))/(float(weight1))
            bl = ((lg/2.0)-R1)/0.125
            sw = sw + x[i]/1000.0*((ii*2.54) - 10)**2
            w = weight1
        sqErr1 = (tW-w)**2
        #sqErr2 = (tI-sw)**2
        Icm = sw-w/1000.0*(R1*2.54-10)**2
        Ibutt = Icm + w/1000.0*(R1*2.54)**2
        sqErr3 = ((w/1000.0*980*R1*2.54)/Ibutt - mgRI)**2
        return -1.0*(sqErr1+sqErr3*1000)
    else:
        n = len(x)
        for i in range(n):
            if i == n-1 and (Length == 27.5 or Length == 28.5):
                ii = Length
            else:
                ii = i
            weight1 = w+x[i]
            r = (lg/2.0) - (bl*0.125)
            R1 = ((w*r)+(x[i]*ii))/(float(weight1))
            bl = ((lg/2.0)-R1)/0.125
            sw = sw + x[i]/1000.0*((ii*2.54) - 10)**2
            w = weight1
        sqErr1 = (tW-w)**2
        sqErr2 = (tI-sw)**2
        return -1.0*(sqErr1+sqErr2)
