# aiaru
about amasing charger
#quick sort 
arr = [10 ,-20 ,12 ,2 ,4, 13, -11, 34, 21]
def quick_sort(arr):
    if len(arr) < 1:
        return arr
    else:
        leading_num = arr[0]
        #itemfromleft = larger than leaging number 
        #itemfromright = smaller than leaging number
        itemfromleft = []
        itemfromright = []
        for a in arr[1:]:
            if a <= leading_num:
                itemfromleft.append(a)
            else:
                itemfromright.append(a)
        return quick_sort(itemfromleft) + [leading_num] + quick_sort(itemfromright)
print(quick_sort(arr))

