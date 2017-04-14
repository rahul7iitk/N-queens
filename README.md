# N-queens
#include<stdio.h>

int count=0;
void set_queens(int add[],int subtract[],int column[],int level,int n);
void  find_count(int n);

int main()
{
    int n;
    scanf("%d",&n);
    
    find_count(n);
    
    printf("%d",count);
    return 0;
}
void  find_count(int n)
{
    int add[n];
    int subtract[n];
    int column[n];
    int level=0;
    
    
    for(int i=0;i<n;i++)
    {
       add[level]=level+i;column[level]=i;
       subtract[level]=level-i;
       set_queens(add,subtract,column,level+1,n);
       
    }
    
}
void set_queens(int add[],int subtract[],int column[],int level,int n)
     {
      if(level==n)  
      {
          count++;
          return ;
      }
     for(int i=0;i<n;i++)
     {
      int flag1=1,flag2=1,flag3=1;
      int p=level+i,q=level-i;
      
      for(int a=0;a<level;a++)
      {
          if(i==column[a])
          {
              flag1=0;
              break;
          }
          if(add[a]==p)
          {
              flag2=0;
              break;
          }
          if(subtract[a]==q)
          {
           flag3=0;
           break;
          }
      }
       if(flag1&&flag2&&flag3)
       {
        add[level]=p;
        subtract[level]=q;
        column[level]=i;
        set_queens(add,subtract,column,level+1,n);
       }
       
     }
     
     }
       
          
     
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
     
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
