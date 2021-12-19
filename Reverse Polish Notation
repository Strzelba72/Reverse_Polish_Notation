#include <iostream>
#include <cassert>
#include <string>

using namespace std;

const int MAX_S = 100;
bool corect_data(string example)
{
    int space=0, operat=0;
    for(int i=0;i<example.size();i++)
    {
        if(!((example[i]>='0' and example[i]<='9')  or example[i]=='.' or example[i]=='+' or example[i]=='-' or example[i]=='*' or example[i]=='/' or example[i]==' '))
        {
            
            return false;
            
        }
        if(example[i]==' ' and example[i-1]==' ')   return false;
        if(example[i]=='.' and (example[i-1]==' ' or example[i+1]==' '))    return false;
        if(example[i]=='0' and (example[i+1]>='0' and example[i]<='9'))     return false;
        if(example[i]=='+' and example[i-1]!=' ')   return false;
        if(example[i]=='-' and example[i-1]!=' ')   return false;
        if(example[i]=='*' and example[i-1]!=' ')   return false;
        if(example[i]=='/' and example[i-1]!=' ')   return false;
        if(example[i]==' ') space++;
        if(example[i]=='+' or example[i]=='-' or example[i]=='*' or example[i]=='/') operat++;
        
        
    }
    if((space/2)!=operat) return false;
    return true;
    
    
}

int main() {
    
    string command;
    string var="";
    double stack[MAX_S];
    int p=0;
    double v1, v2;  
    int start=0,end=0;
    
    
    
    do
    {
      getline(cin,command);  
    }
    while(corect_data(command)==0);
    
    
    
    for(int i=0;i<command.size();i++)
    {
       
        
        if(command[i]!=' ' and command[i]!='+' and command[i]!='-' and command[i]!='*' and command[i]!='/')
        {
        
        var+=command[i];
        }
        else if(command[i]==' ')
        {
            if(command[i-1]!='+' and command[i-1]!='-' and command[i-1]!='*' and command[i-1]!='/')
            {
                stack[p++]=stod(var);
                //cout<<var<<endl;
                var="";
            }
        }
        else if(command[i]=='+' or command[i]=='-' or command[i]=='*' or command[i]=='/')
        {
            v2 = stack[ --p ];  
            v1 = stack[ --p ];
            
            switch( command[i] ) 
            {
                case '+' : v1 += v2; break;
                case '-' : v1 -= v2; break;
                case '*' : v1 *= v2; break;
                case '/' : v1 /= v2; break;
            }
            stack[p++] = v1;
            
        }
      
    }
    cout << stack[--p] << endl;
     
    
    
    
    
    return 0;
}
