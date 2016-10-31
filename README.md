# c-
lian xi
#include "stdafx.h"
#include"iostream"
using namespace std;
class CObj
{
public:
	void indata();
	void outdata();
	CObj();
	CObj(CObj &op);

private:
	char name[20];
	int age;
	
};
CObj::CObj()
{
	strcpy_s(name, "aaa");
	age = 000;
	cout << "默认构造函数(姓名):" << name << endl;
	cout << "默认构造函数(年龄):" << age << endl;
}
CObj::CObj(CObj &op)
{
	age = op.age * 4;
	strcpy_s(name, op.name);
	cout << "复制构造函数(姓名):" << op.name << endl;
	cout << "复制构造函数(年龄):" << op.age*4 << endl;
}
void CObj::indata()
{
	cin >> name;
	cin >> age;
}

void CObj::outdata()
{
	cout << "姓名:" << name << endl;
	cout << "年龄:" << age << endl;
}

int main()
{
	CObj s01;
	s01.indata();
	s01.outdata();
	CObj s02(s01);
	s02.outdata();


}
