#include<iostream>
using namespace std;

class car{
public:
    int year;
    char model[20];
    int speed;
    float volume;
    bool start();
    void go(int dir);
    void goBackward();
    void goForward();
    void stop();
    void getdata();
    void showdata();
};

bool car::start(){
    return true;
}
void car::go(int dir){
    if(start()==true){
        if(dir==1)
            goForward();
        if(dir==0)
            goBackward();
        else
        if(speed==0){
            cout<<"mashin zogsoj bna";
        }else
            stop();
    }
}
void car::goForward(){
    speed = speed+5;
}
void car::goBackward(){
    speed = speed-5;
}
void car::stop(){
    speed = 0;
}
void car :: getdata()
{
    cout<<"\nEnter car Year:";
    cin>>year;
    cout<<"\nEnter car Model:";
    cin>>model;
    cout<<"\nEnter car speed:";
    cin>>speed;
    cout<<"\nEnter car Volume:";
    cin>>volume;

}

void car :: showdata()
{
    cout<<"\t"<<year;
    cout<<"\t"<<model;
    cout<<"\t"<<speed<<"km/h";
    cout<<"\t"<<volume<<endl;
}
int main(){
    car car[10];
    int n;
    cout<<"\nHed hurtelh car-iin medeelel awah we?: ";
    cin>>n;

    for(int i=0; i<n; i++){
        car[i].getdata();
    }

    cout<<endl<<"#\t"<<"Year\t" << "Model\t" << "speed\t" << "volume\t"<< endl;
    for(int i=0; i<n; i++){
        cout<<i;
        car[i].showdata();
    }
    int i,c;
    cout<<"ymar mashinii hurdiig uurchluh we? ";
    cin>>i;

        cout << "          Menu         " << endl;
        cout << "-----------------------" << endl;
        cout << " 1. Hurdaa nemeh       " << endl;
        cout << " 2. Hurdaa hasah,uhrah " << endl;
        cout << " 3. hurdaa hasj zogsoh " << endl;
        cout << "-----------------------" << endl;
        cout << "\nhurdaa tohiruulna uu: ";
        cin >> c;
        switch (c)
        {
            case 1: cout <<i<<"-r mashinii hurd nemegdeed... ";
                    car[i].go(1);
                    cout<<car[i].speed<<"km/h";
                    break;
            case 2: cout <<i<<"-r mashinii hurd hasagdaad... ";
                    car[i].go(0);
                    cout<<car[i].speed<<"km/h";
                    break;
            case 3: cout << "Mashin zogsow: ";
                    car[i].go(2);
                    cout<<car[i].speed<<"km/h";
                    break;
        }
    return 0;
}
