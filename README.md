# Devtailor_solution

Solution for array problem


```dart

import 'dart:core';

void main(){
  print(ArrayChallenge([1,2,5,12]));
}
  

int ArrayChallenge(List arr) {

  // The fuction starts with sublisting the given input array(2).
  // first element of the sublisted array is taken as reference Index (3) and 
  // the value is compared with every other ascending index(6) through mapping(5) 
  // if the next values is greater than the reference index, profit for that indexes are calculated
  //  and stored in local var(7), then all greatest values among each iteration is 
  // stored in profits list(1, 7) and at last the largest profit margin among the list (1)
  // is returned if the list is not null. If null the function returns -1
  
  
  //1
  List<int> profits = [];

  for(int i = 0; i < arr.length ; i++){
    
    //2
    List newList = arr.sublist(i).toList();
    
    //3
    int refIndex = newList.first;
    
    //4
    int profit = 0;
  
    //5
    newList.map((e){
      
      //6
      if(e > refIndex){
        
        int indexProfit = e - refIndex;
        
        //7
        if(indexProfit > profit){
         
          profit = indexProfit;
          profits.add(profit);
        }
      }  
    }).toList();
  }

  if(profits.isNotEmpty){
    //8
    return profits.reduce((present, prev) => present > prev ? present: prev);
  }else{
    return -1;
  }
}

```

