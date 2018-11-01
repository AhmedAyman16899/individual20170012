# individual20170012
#include <iostream>

using namespace std;
class pet {
protected :
        string name;
        bool neuterSpayed;
        bool talks;
public :
    void set_values(string a ,bool b , bool c ){
        name = a ;
        neuterSpayed = b ;
        talks = c ;

    }
    virtual void printDescription()=0;
};

class cat : public pet {
private:
public:
    void printDescription(){
    cout << name << "   " << neuterSpayed << endl  ;
    }
};

class dog : public pet {
private:
public:
    void printDescription(){
    cout << name << "   " << neuterSpayed << endl   ;
    }
};

class bird : public pet {
private:
public:
    void printDescription(){
    cout << name << "   "  << talks << endl ;
    }
};
int main()
{
   // cout << "Hello world!" << endl;
    //cout << 1+5 ;
    cat caat ;
    dog doog ;
    bird birdd ;
    //pet *p1 , *p2 , *p3 ;
    pet *p1 = &caat ;
    pet *p2 = &doog;
    pet *p3 = &birdd;
    p1->set_values("cat" , 0 , 1 );
    p2->set_values("dog" , 1 , 0 );
    p3->set_values("bird" ,  0, 1 );
    //cout << p2-> printDescription() << endl;


    pet *p [3] = {&caat , &doog , &birdd};
    for (int i =0 ; i<3 ; i++){

       p[i]->printDescription();
       cout << endl;
    }


    return 0;
}
