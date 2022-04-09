# Java-Program-to-find-the-frequency-of-a-word-in-a-given-text

import java.io.*;

 class frequencyofword
  {
    public static void main(String args[])throws IOException
     {
      BufferedReader br=new BufferedReader(new InputStreamReader(System.in));
      
      System.out.print("Enter the sentence = ");
      String s=br.readLine();
      
      s = s + " ";
      int len=s.length();
      s=s.toLowerCase();

      System.out.print("Enter the word whose frequency is to be determined = ");
      String w=br.readLine();
  
      String s1="",s2,s3="";
      char ch,ch1,ch2,curr='\u0000', prev='\u0000';
      
      int ind=0,part=0;
      
      for(int i=0; i<len; i++)
      {
          ch=s.charAt(i);
          
          if(ch==' ')
          {
              if(s1.equalsIgnoreCase(w)==true)
                    ind++;
                 
                  s1 = s1 + ch;
                  
            
               for(int j=0; j<s1.length(); j++)
                 {
                     
                    curr = s1.charAt(j);
                    s2 = "" + prev + curr;
                    
                    if(s2.equalsIgnoreCase(w) == true)
                        part++;
                     
                        
                        s2="";
                        
                    prev = curr;
                    }
                   
                    s1="";
                }
              
              
              
            
            
           else
              s1=s1+ch;
        }
        System.out.println(w+" occurs as an independent word "+ind+" times");
        System.out.println(w+" occurs as a part of A word = "+ (part-ind)+" times" );
    }
}   



