#include<iostream>
#include<string>

using namespace std;

class Bands
{
	protected:
		int count;
		virtual void setcount(int count)=0;
};

class Metal:Bands
{
	private:
		int pyrotechnicians;
	public:
		void setcount(int count);
		int getband(void);
		int getpyrotechnicians(void);
		void setpyrotechnicians(int pyrotechnicians);
		void removepyrotechnicians(int size);
		void addpyrotechnicians(int size);
		void addmembers(int size);
		void removemembers(int size);
};

void Metal::addmembers(int size)
{
	count=count+size;
}

void Metal::addpyrotechnicians(int size)
{
	pyrotechnicians=pyrotechnicians+size;
}

void Metal::removemembers(int size)
{
	count=count-size;
}

void Metal::removepyrotechnicians(int size)
{
	pyrotechnicians=pyrotechnicians-size;
}

void Metal::setpyrotechnicians(int pyrotechnicians)
{
	this->pyrotechnicians=pyrotechnicians;
}

void Metal::setcount(int count)
{
	this->count=count;
}

int Metal::getband(void)
{
	return this->count;
}

int Metal::getpyrotechnicians(void)
{
	return this->pyrotechnicians;
}

class Symphony:Bands
{
	private:
		string conductor;
	public:
		void setcount(int count);
		int getband(void);
		string getconductor(void);
		void setconductor(string conductor);
		void add(int size);
		void remove(int size);
};

void Symphony::remove(int size)
{
	count=count-size;
}

void Symphony::add(int size)
{
	count=count+size;
}

void Symphony::setconductor(string conductor)
{
	this->conductor=conductor;
}

void Symphony::setcount(int count)
{
	this->count=count;
}

int Symphony::getband(void)
{
	return this->count;
}

string Symphony::getconductor(void)
{
	return this->conductor;
}

class Jazz:Bands
{
	public:
		void setcount(int count);
		int getcount(void);
		void addmember(int size);
		void removemember(int size);
};

void Jazz::addmember(int size)
{
	count=count+size;
}

void Jazz::removemember(int size)
{
	count=count+size;
}

void Jazz::setcount(int count)
{
	this->count=count;
}

int Jazz::getcount(void)
{
	return this->count;
}

class Marching:Bands
{
	private:
		
	public:
		void setcount(int count);
		int getcount(void);
		void addmembersand(int size);
		void removemembersand(int size);
};

void Marching::addmembersand(int size)
{
	count=count+size;
}

void Marching::removemembersand(int size)
{
	count=count-size;
}

void Marching::setcount(int count)
{
	this->count=count;
}

int Marching::getcount(void)
{
	return this->count;
}

int main(void)
{
	while(1)
	{
	int myint1;
	int myint2;
	int count;
	cout<<"Welcome to your Music Bands Archive :D"<<endl;
	cout<<"Please press 1 to enter data for metal band"<<endl;
	cout<<"Please press 2 to enter data for symphony band"<<endl;
	cout<<"Please press 3 to enter data for jazz band"<<endl;
	cout<<"Please press 4 to enter data for marching band"<<endl;
	cin>>myint1;
	if(myint1==1)
	{
		int pyrotechnicians;
		Metal metal;
		cout<<"Please enter the number of members for the metal band:";
		cin>>count;
		metal.setcount(count);
		cout<<"Please enter the number of pyrotechnicians for the metal band:";
		cin>>pyrotechnicians;
		metal.setpyrotechnicians(pyrotechnicians);
		cout<<"The total band members for the metal band are: "<<count<<endl;
		cout<<"The total number of pyrotechnicians for the metal band are: "<<pyrotechnicians<<endl;
		cout<<"What do you want to do with the members of the band?"<<endl;
		cout<<"Please press 6 to remove members"<<endl;
		cout<<"Please press 7 to add members"<<endl;
		cout<<"Please press 8 to remove pyrotechnicians"<<endl;	
		cout<<"Please press 9 to add pyrotechnicians"<<endl;	
		cin>>myint2;
		if(myint2==6)
		{
			cout<<"Please enter the number of members you want to remove:";
			cin>>count;
			metal.removemembers(count);
			cout<<endl;
		}
		if(myint2==7)
		{
			cout<<"Please enter the number of members you want to add:";
			cin>>count;
			metal.addmembers(count);
			cout<<endl;
		}
		if(myint2==8)
		{
			cout<<"Please enter the number of pyrotechnicians you want to remove:";
			cin>>count;
			metal.removepyrotechnicians(count);
			cout<<endl;
		}
		if(myint2==9)
		{
			cout<<"Please enter the number of pyrotechnicians you want to add:";
			cin>>count;
			metal.addpyrotechnicians(count);
			cout<<endl;
		}
		cout<<"The total number of band members are: "<<metal.getband()<<endl;
		cout<<"The total number of pyrotechnicians are: "<<metal.getpyrotechnicians()<<endl;
	}
	if(myint1==2)
	{
		string conductor;
		Symphony symph;
		cout<<"Please enter the number of members for Symphony:";
		cin>>count;
		symph.setcount(count);
		cout<<"Please enter the name of the conductor:";
		cin>>conductor;
		symph.setconductor(conductor);
		cout<<"The total number of band members are: "<<count<<endl;
		cout<<"The name of the conductor is: "<<conductor<<endl;
	 	cout<<"What do you want to do with the members of the band?"<<endl;
		cout<<"Please press 6 to remove members"<<endl;
		cout<<"Please press 7 to add members"<<endl;
		cin>>myint2;
		if(myint2==6)
		{
			cout<<"Please enter the number of members you want to remove:";
			cin>>count;
			symph.remove(count);
			cout<<endl;
		}
		if(myint2==7)
		{
			cout<<"Please enter the number of members you want to add:";
			cin>>count;
			symph.add(count);
			cout<<endl;
		}
		cout<<"The total number of band members are: "<<symph.getband()<<endl;
		cout<<"The name of the conductor is: "<<symph.getconductor()<<endl;
	}
	if(myint1==3)
	{
		Jazz jazz;
		cout<<"Please enter the number of members for Jazz:";
		cin>>count;
		jazz.setcount(count);
		cout<<"The total number of band members are: "<<count<<endl;
		cout<<"What do you want to do with the members of the band?"<<endl;
		cout<<"Please press 6 to remove members"<<endl;
		cout<<"Please press 7 to add members"<<endl;	
		cin>>myint2;
		if(myint2==6)
		{
			cout<<"Please enter the number of members you want to remove:";
			cin>>count;
			jazz.removemember(count);
			cout<<endl;
		}
		if(myint2==7)
		{
			cout<<"Please enter the number of members you want to add:";
			cin>>count;
			jazz.addmember(count);
			cout<<endl;
		}
		cout<<"The total number of band members are: "<<jazz.getcount()<<endl;
	}
	if(myint1==4)
	{
		Marching me;
		cout<<"Please enter the number of members for Marching:";
		cin>>count;
		me.setcount(count);
		cout<<"The total number of band members are: "<<count<<endl;
		cout<<"What do you want to do with the members of the band?"<<endl;
		cout<<"Please press 6 to remove members"<<endl;
		cout<<"Please press 7 to add members"<<endl;
		cin>>myint2;
		if(myint2==6)
		{
			cout<<"Please enter the number of members you want to remove:";
			cin>>count;
			me.removemembersand(count);
			cout<<endl;
		}
		if(myint2==7)
		{
			cout<<"Please enter the number of members you want to add:";
			cin>>count;
			me.addmembersand(count);
			cout<<endl;
		}
		cout<<"The total number of band members are: "<<me.getcount()<<endl;
	}
	}
}
