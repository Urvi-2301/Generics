using System;
using System.Collections.Generic;
using System.Linq;

public class GenericValueTypeContainer<T> where T : struct
{
    private List<T> valueList;

    public GenericValueTypeContainer()
    {
        valueList = new List<T>();
    }

    
    public void AddItem(T item)
    {
        valueList.Add(item);
    }

   
    public T GetItem(int index)
    {
        if (index >= 0 && index < valueList.Count)
        {
            return valueList[index];
        }
        else
        {
            throw new ArgumentOutOfRangeException(nameof(index), "Index is out of range");
        }
    }


    public List<T> GetSortedDescending()
    {
        List<T> sortedList = valueList.OrderByDescending(x => x).ToList();
        return sortedList;
    }
}
