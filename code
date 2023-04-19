#include <iostream>
#include <queue>
#include <vector>
#include <cstring>
using namespace std;
const int specializations=20;
const int patient =5;
vector<deque<string>>names(20);
vector<deque<int>>que(20);
int qu[specializations];
vector<int>spq(20,0);
void add_new_patient(){
     string name;
     int status,sp;
     cout<<"enter name:"<<flush;
     cin>>name;
     cout<<"enter status:"<<flush;
     cin>>status;
     cout<<"enter specialization:"<<flush;
     cin>>sp;
     qu[sp-1]++;
     if(qu[sp-1]>5){
          cout<<"sorry,this specialization is full"<<endl;
     }else{
         if(status==1){
               if(spq[sp-1]>0){
                    string h=names[sp-1].front();
                    names[sp-1].pop_front();
                    que[sp-1].push_front(1);
                    names[sp-1].push_front(name);
                    names[sp-1].push_front(h);
               }else{
                    que[sp-1].push_front(1);
                    names[sp-1].push_front(name);
               }
               spq[sp-1]++; 
          }else{
               que[sp-1].push_back(0);
               names[sp-1].push_back(name);
          } 
     }
}
void print_all_patients(){
     for(int i=0;i<20;i++){
          if(qu[i]>0){
               string s="";
               int cnt=0;
               cout<<"there are "<<qu[i]<<" patient in specialization "<<i+1<<endl;
               for(int j=0;j<qu[i];j++){
                    (que[i][cnt]==1)?s="reqular":s="unreguler";
                    cout<<names[i][cnt++]<<" "<<s<<endl;
               }
          }
     }
}
void next_patient(){
          int sp;
          cout<<"Enter specialization: "<<flush;
          cin>>sp;
          cout<<names[sp-1].front()<<" please go with Dr"<<endl;
          names[sp-1].pop_front();
          que[sp-1].pop_front();
          qu[sp-1]--;
}
int main(){
     int choose ;
     bool again=true;
     cout<<"           WELCOME IN HOSPITAL SYSTEM"<<endl;
     while(again){
          cout<<"1-> New patient"<<endl;
          cout<<"2-> Print all patient "<<endl;
          cout <<"3-> Get next patient"<<endl;
          cout <<"4-> Exit"<<endl;
          cin>>choose;
          if(choose==1){
               add_new_patient();
          }else if (choose==2){
               print_all_patients();
          }else if (choose==3){
               next_patient();
          }else if(choose==4){
               cout<<"           THANK YOU "<<endl;
               again=false;
          }
     }
}
