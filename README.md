#include<iostream>
#include<iomanip>
#include<math.h>
#include<string.h>
#include <ctype.h>
#include <fstream>

using namespace std;
class Xe
{
	protected:
	string TenNguoiThue;
	string Sdt;
	int Nsinh;
	string add;
	string cmnd;
	float Sogiothue;
	int Loaixe;
	public:

	virtual void NhapTT()
	{
		cout<<"Nhap Ten Nguoi Thue : ";
		getline(cin,TenNguoiThue);
		cout<<"Nhap So dien thoai : ";
		getline(cin,Sdt);
		cout<<"Nhap Nam sinh : ";
		cin>>Nsinh;
		cin.ignore();
		cout<<"Nhap Dia chi : ";
		getline(cin,add);
		cout<<"Nhap cmnd : ";
		getline(cin,cmnd);
		cout<<"Nhap So gio thue : ";
		cin>>Sogiothue;
		cout<<"Nhap Loai xe : ";
		cin>>Loaixe;
		ofstream file;
        file.open("D:\\"+cmnd+".txt", ios::out | ios::app );
        file<<TenNguoiThue<<endl<<Sdt<<endl<<Nsinh<<endl<<add<<endl<<cmnd<<endl<<Sogiothue<<endl;
        file<<"-------------------------------"<<endl;
        file.close();
	}
	virtual void Xuat()
	{
	    cout<<"Ho Ten : "<<TenNguoiThue<<"\t So dien thoai : "<<Sdt<<"\t Nam sinh : "<<Nsinh<<endl;
	    cout<<"Dia chi : "<<add<<"\t cmnd : "<<cmnd<<"\t So gio thue : "<<Sogiothue<<endl;
	}
};
class XeHaiBanh:public Xe{
	private:
		string kieuxe;
		string mauson;
		string nhanhieu;
	public: 
	void NhapTT(){
		cout<<"Kieu xe: ";
		getline(cin, kieuxe);
		cin.ignore();
		cout<<"Mau son xe: ";
		getline(cin, mauson);
		cin.ignore();
		cout<<"Nhan hieu: ";
		getline(cin, nhanhieu);
	}
	void Xuat(){
		cout<<"Kieu xe: "<<kieuxe<<" Mau son xe: "<<mauson<<" Nhan hieu: "<<nhanhieu<<endl;
	}
};
class XeBonBanh:public Xe{
	private:
		string banglai;
		string bienso;
		string nhanhieu;
		string kieuxe;
	public: 
	void NhapTT(){
		cout<<"Bang lai: ";
		getline(cin, banglai);
		cin.ignore();
		cout<<"Bien so: ";
		getline(cin, bienso);
		cin.ignore();
		cout<<"Nhan Hieu: ";
		getline(cin, nhanhieu);
		cout<<"Kieu xe: ";
		getline(cin, kieuxe);
	}
	void Xuat(){
		cout<<"Bang lai: "<<banglai<<" Bien so: "<<bienso<<" Nhan hieu: "<<nhanhieu<<"Kieu xe: "<<kieuxe<<endl;
	}
};
int main(){	
	Xe obj1;
	obj1.NhapTT();
	obj1.Xuat();\
	
	XeHaiBanh obj2;
	obj2.NhapTT();
	obj2.Xuat();
	return 0;
}
