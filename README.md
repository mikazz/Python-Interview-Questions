# Python-Interview-Questions


# What will be the output of the code below? Explain your answer. How would you modify the definition of extendList to produce the presumably desired behavior?


    def extendList(val, list=[]):
        """
            New default list is created only once when
            the function is defined, and that same list
            is then used subsequently whenever extendList
            is invoked without a list argument being specified.
            This is because expressions in default arguments
            are calculated when the function is defined,
            not when it’s called.

        """
        
        list.append(val)
        return list

    list1 = extendList(10)
    list2 = extendList(123,[])
    list3 = extendList('a')

    print "list1 = %s" % list1
    print "list2 = %s" % list2
    print "list3 = %s" % list3


    def extendList(val, list=None):
        if list is None:
            list = []
        list.append(val)
        return list

    list1 = extendList(10)
    list2 = extendList(123,[])
    list3 = extendList('a')

    print "list1 = %s" % list1
    print "list2 = %s" % list2
    print "list3 = %s" % list3

    
# What will be the output of the code below? Explain your answer. How would you modify the definition of multipliers to produce the presumably desired behavior? (Late binding)


def multipliers():
    return [lambda x : i * x for i in range(4)]

print [m(2) for m in multipliers()]

