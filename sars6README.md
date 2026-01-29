Probleam Statement:

You are given an array of strings wordsDic called wordsDict containing N strings.
You are also given Q queries. In each query, you are given two distinct words word1 and word2 that are guaranteed to appear in the array.
Your task is to determine the minimum distance between any occurrence of word1 and any occurrence of word2 in the array.

CODE:

class BeingZero {
    public int[] minimumDistanceII(String[] w, String[][] q) {
        //write your code here

        Map<String,List<Integer>> m=new HashMap<>();
        // Map<String,List<Integer>> ans=new HashMap<>();
        

        int k=0;
        for(String str:w){
            // m.put(str,m.getOrDefault(str,new ArrayList<>()))
            if(!m.containsKey(str)) m.put(str,new ArrayList<>());
            m.get(str).add(k);
            k++;
        }

        int ans[]=new int[q.length];

        int idx=0;

        
        for(String a[]:q){

            String str1=a[0];
            String str2=a[1];
            int min=Integer.MAX_VALUE;

            List<Integer> l1=m.get(str1);
            List<Integer> l2=m.get(str2);

            int i=0,j=0;
            while(i<l1.size()  &&  j<l2.size()){

                min=Math.min(Math.abs(l1.get(i)-l2.get(j)),min);

                if(l1.get(i)<l2.get(j)) i++;
                else j++;
                
            }
            ans[idx++]=min;
            
        }
        return ans;
    }
}
