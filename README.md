class Solution{
public:
	int search(string pat, string txt) {
	    int k=pat.size();
	    map<char,int>mp;
	    for(int a=0;a<k;a++)
	    {
	        mp[pat[a]]++;
	    }
	    int count=mp.size();
	    int res=0;
	    int i=0,j=0;
	    while(j<txt.size())
	    {
	        mp[txt[j]]--;
	      
		if(mp[txt[j]]==0)
		count--;
	       
	       if(j-i+1<k)
	       j++;
	       else if(j-i+1==k)
	       {
	           if(count==0)
	           res++; 
	           if(mp.find(txt[i])==mp.end())
	           {
	               i++;
	              
	           }
	           else
	           mp[txt[i]]++;
	           if(mp[txt[i]]==1)
	           count++;
	             i++; 
	          j++;
	           
	       }
	    }
	    return res;
	}

};
