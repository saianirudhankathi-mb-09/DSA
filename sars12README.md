Problem Statement:

You are given an array of strings wordsDict, containing N words in a fixed order.
You are also given two strings word1 and word2, and it is guaranteed that both words appear at least once in the array.
Your task is to determine the minimum distance between word1 and word2 in the array.
If word1 and word2 are the same word, then you must find the minimum distance between two different occurrences of that word in the array.

CODE:

class BeingZero {
    public int minimumDistanceIII(String[] w, String w1, String w2) {
        //write your code here
        int min=Integer.MAX_VALUE,a=-1,b=-1;

        for(int i=0;i<w.length;i++){
            if(w1.equals(w2)){
                if(w[i].equals(w1)){
                    if(a==-1){
                        a=i;
                    }
                    else if(b==-1){
                        b=i;
                    }
                    else{
                        if(b>a){
                            a=i;
                        }
                        else{
                            b=i;
                        }
                    }
                    
                    if((a!=-1  &&  b!=-1)  &&  a!=b){
                        min=Math.min(min,Math.abs(a-b));
                    }
                    
                }    
            }
            else{
                if(w[i].equals(w1)){
                    a=i;
                }
                if(w[i].equals(w2)){
                    b=i;
                }
                if((a!=-1  &&  b!=-1)  &&  a!=b){
                    min=Math.min(min,Math.abs(a-b));
                }
            }
        }

        if((a!=-1  &&  b!=-1)  &&  a!=b){
            min=Math.min(min,Math.abs(a-b));
        }
        // if(w[i].equals(w1)){
        //     l1.add(i);
        // }
        // if(w[i].equals(w2)){
        //     l2.add(i);
        // }
        // List<Integer> l1=new ArrayList<>();
        // List<Integer> l2=new ArrayList<>();
        // for(int e1:l1){
        //     for(int e2:l2){
        //         if(e1!=e2){
                    
        //             min=Math.min(min,Math.abs(e1-e2));
        //         }
        //     }
        // }
        return min;
    }
}
