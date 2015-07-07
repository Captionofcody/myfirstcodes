# myfirstcodes
owned self for testing
#include<iostream>
using namespace std;
class complex 
     {
     	double real;
     	double img;
		 public:
     	complex():real(0),img(0){};
     	complex(double r,double i){real=r;img=i;};
     	double showreal(){return real;	};
     	double showimg(){return img;}
     	 void show(){
     		cout<<this->real<<"+/-"<<this->img<<"i"<<endl;
     	};
     	complex operator +(complex&);
     	complex operator +(double);
     	bool operator ==(complex&);
     	complex operator ++();
     	complex operator ++(int);
		 ~complex(){};	         
     };
    complex complex::operator +(complex&c)
                                 {
                                 	complex temp;
                                 	temp.real=real+c.real;
                                 	temp.img=img+c.img;
                                 	return temp;
                                 }
    complex complex::operator +(double a)
	                            {
	                            	complex temp;
                                 	temp.real=real+a;
                                 	temp.img=img;
                                 	return temp;	
	                            }
   bool complex ::operator ==(complex&c)
                               {
                               	if((real==c.real)&&(img==c.img))return true;
                               	else return false;
                               }
  complex complex:: operator ++()
                      {
                      	real+=1;
                      	return *this;
                      }
  complex complex:: operator ++(int)
                      {
                      	real+=1;
                      	return *this;
                      }
int main()
    {
      complex com1(4,5),com2(4,5),com3;
      com1.show();com2.show();com3.show();
      com3=com1+com2;com3.show();
      com1++;++com1;com1.show();
      if(com2==com1){cout<<"这两个复数相等";}
      else {com2.show();com1.show();cout<<"显然二者不等";}
      return 0 ;
    } 