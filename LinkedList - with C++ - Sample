#include <cstdlib>
#include <iostream>
#include <fstream>
#include <string.h>
#include <cstdlib>
using namespace std;

class DoublyNode {
public:
	string ad;		
	string soyad;
	int numara;
	int dersAlis;
	int yandalciftdal;
	DoublyNode* next;
	DoublyNode* back;	
};

class DoublyNodeOther {
public:
	string ad;	
	string soyad;
	int numara;
	int dersAlis;
	int yandalciftdal;
	DoublyNodeOther* next;		
	DoublyNodeOther* back;
};

class ProgramlamaList {
public:
	ProgramlamaList(void) { head = NULL; }	
	~ProgramlamaList(void);			
	bool IsEmpty() { return head == NULL; }
	DoublyNode* InsertNode(string ad,string soyad,int numara,int dersAlis,int yandalciftdal);	
	int FindNode(int numara);	
	int DeleteNode(int numara);
	void DisplayList(void);
	void DigerListeleme1();
	void DigerListeleme2();
	void DigerListeleme3();
	void DigerListeleme5();
public:
	DoublyNode* head;
};

class VeriList {
public:
	VeriList(void) { head = NULL; }	
	~VeriList(void);				
	bool IsEmpty() { return head == NULL; }
	DoublyNodeOther* InsertNode(string ad,string soyad,int numara,int dersAlis,int yandalciftdal);	
	int FindNode(int numara);	
	int DeleteNode(int numara);
	void DisplayList(void);
	void DigerListeleme1();
	void DigerListeleme4();
public:
	DoublyNodeOther* head;
};

ProgramlamaList plist; VeriList vlist;
DoublyNode* ProgramlamaList::InsertNode(string ad,string soyad,int numara,int dersAlis,int yandalciftdal) {
	DoublyNode* currNode=head;
	DoublyNode* newNode=new DoublyNode;
	newNode->ad=ad;	
	newNode->soyad=soyad;	
	newNode->numara=numara;	
	newNode->dersAlis=dersAlis;	
	newNode->yandalciftdal=yandalciftdal;
	newNode->next=head;
	if(head != NULL ) head->back = newNode;
    	head = newNode;
   	 newNode->back = NULL;
	return newNode;
}
DoublyNodeOther* VeriList::InsertNode(string ad,string soyad,int numara,int dersAlis,int yandalciftdal) {
	DoublyNodeOther* currNode=head;
	DoublyNodeOther* newNode	=	new	DoublyNodeOther;
	newNode->ad=ad;
	newNode->soyad=soyad;
	newNode->numara=numara;
	newNode->dersAlis=dersAlis;
	newNode->yandalciftdal=yandalciftdal;
	newNode->next=head;
	if(head != NULL ) head->back = newNode;
   	 head = newNode;
   	 newNode->back = NULL;
	return newNode;
}

int ProgramlamaList::FindNode(int numara) {
	DoublyNode* currNode	=	head;
	int currIndex	=	1;
	while (currNode && currNode->numara != numara) {
		currNode	=	currNode->next;
		currIndex++;
	}
	if (currNode) return currIndex;
	return 0;
}

int VeriList::FindNode(int numara) {
	DoublyNodeOther* currNode=head;
	int currIndex=1;
	while (currNode && currNode->numara != numara) {
		currNode=currNode->next;
		currIndex++;
	}
	if (currNode) return currIndex;
	return 0;
}

int ProgramlamaList::DeleteNode(int numara) {
	DoublyNode* prevNode=NULL;         
  DoublyNode* currNode=head;         
  int currIndex=1;
	while (currNode && currNode->numara != numara) {
		prevNode	=	currNode;
		currNode	=	currNode->next;
		currIndex++;
	}
	if (currNode) {
		if (prevNode) {
			prevNode->next=currNode->next;
			delete currNode;
		}
		else {
			head=currNode->next;
			delete currNode;
		}
		return currIndex;
	}
	return 0;
}

int VeriList::DeleteNode(int numara) {
	DoublyNodeOther* prevNode=NULL;   DoublyNodeOther* currNode=head;   int currIndex=1;
	while (currNode && currNode->numara != numara) {
		prevNode=currNode;
		currNode=currNode->next;
		currIndex++;
	}
	if (currNode) {
		if (prevNode) {
			prevNode->next=currNode->next;
			delete currNode;
		}
		else {
			head=currNode->next;
			delete currNode;
		}
		return currIndex;
	}
	return 0;
}

void ProgramlamaList::DisplayList(){
   int num=0;
   DoublyNode* currNode=head;
   while (currNode != NULL){
	cout <<currNode->numara<<" "<<currNode->ad<<" "<<currNode->soyad << endl;
	currNode=currNode->next;
	num++;
   }
   cout << "Ogrenci Sayisi : " << num << endl;
}
void VeriList::DisplayList(){
   int num=0;
   DoublyNodeOther* currNode=head;
   while (currNode != NULL){
	cout <<currNode->numara<<" "<<currNode->ad<<" "<<currNode->soyad << endl;
	currNode=currNode->next;
	num++;
   }
   cout << "Ogrenci Sayisi : " << num << endl;
}

ProgramlamaList::~ProgramlamaList(void) {
   DoublyNode* currNode=head, *nextNode=NULL;
   while (currNode != NULL)
   {
	nextNode=currNode->next;
	delete currNode;	
	currNode=nextNode;
   }
}

VeriList::~VeriList(void) {
   DoublyNodeOther* currNode=head, *nextNode=NULL;
   while (currNode!=NULL)
   {
	nextNode=currNode->next;
	delete currNode;	
	currNode=nextNode;
   }
}

ProgramlamaList kriter;
void ProgramlamaList::DigerListeleme1(){
	DoublyNode* newNode=head;
	while(newNode!=NULL){
		if(newNode->dersAlis>1) kriter.InsertNode(newNode->ad,newNode->soyad,newNode->numara,newNode->dersAlis,newNode->yandalciftdal);
		newNode=newNode->next;
	}
}

void VeriList::DigerListeleme1(){
	DoublyNodeOther* doublyOtherNode=head;
	while(doublyOtherNode!=NULL){
		if(doublyOtherNode->dersAlis>1 && kriter.FindNode(doublyOtherNode->numara)!=0) cout<<"Numara:"<<doublyOtherNode->numara<<" Ad:"<<doublyOtherNode->ad<<" Soyad:"<<doublyOtherNode->soyad<<endl;
		doublyOtherNode=doublyOtherNode->next;
	}
}

void ProgramlamaList::DigerListeleme2(){
	DoublyNode* newNode	= head;
	while(newNode!=NULL){
		if(vlist.FindNode(newNode->numara)==0){
			cout<<"Numara:"<<newNode->numara<<" Ad:"<<newNode->ad<<" Soyad:"<<newNode->soyad<<endl;
		}
		newNode=newNode->next;
	}
}

void ProgramlamaList::DigerListeleme3(){
	ProgramlamaList programlamaAgrubu;
	ProgramlamaList programlamaBgrubu; 
	DoublyNode* current = head;
	while(current != NULL)
	{
		if(current->soyad.substr(0,1) <= "k")
		{
			programlamaAgrubu.InsertNode(current->ad,current->soyad,current->numara,current->dersAlis,current->yandalciftdal);
		}
		if(current->soyad.substr(0,1) > "k")
		{
			programlamaBgrubu.InsertNode(current->ad,current->soyad,current->numara,current->dersAlis,current->yandalciftdal);
		}
		current = current -> next;
	}
	cout<<"Bilgisayar Programlama A Grubu"<<endl;
	cout<<"---------------------------"<<endl;
	programlamaAgrubu.DisplayList();
	cout<<"Bilgisayar Programlama B Grubu"<<endl;
	cout<<"---------------------------"<<endl;
	programlamaBgrubu.DisplayList();
}

void VeriList::DigerListeleme4(){
	VeriList veriAgrubu;
	VeriList veriBgrubu;
	DoublyNodeOther* current = head;
	while(current != NULL)
	{
		if(current->soyad.substr(0,1) <= "k")
		{
			veriAgrubu.InsertNode(current->ad,current->soyad,current->numara,current->dersAlis,current->yandalciftdal);
		}
		if(current->soyad.substr(0,1) > "k")
		{
			veriBgrubu.InsertNode(current->ad,current->soyad,current->numara,current->dersAlis,current->yandalciftdal);
		}
		current = current -> next;
	}
	cout<<"---------------------------"<<endl;
	cout<<"Veritabani Yonetim Sistemleri A Grubu"<<endl;
	veriAgrubu.DisplayList();
	cout<<"---------------------------"<<endl;
	cout<<"Veritabani Yonetim Sistemleri B Grubu"<<endl;
	veriBgrubu.DisplayList();
}

void ProgramlamaList::DigerListeleme5(){
	DoublyNode* newNode= head;
	while(newNode!=NULL){
		if(vlist.FindNode(newNode->numara)!=0 && newNode->yandalciftdal==1){
			cout<<"Numara:"<<newNode->numara<<" Ad:"<<newNode->ad<<" Soyad:"<<newNode->soyad<<endl;
		}
		newNode=newNode->next;
	}
}

void HizliSiralama(){
	DoublyNode *i,*pivot,*temp,*j,*newpivot,*ensag;
	DoublyNode* newNode=plist.head;
	ProgramlamaList gecici,yazdir;
	while(newNode!=NULL){
		if(vlist.FindNode(newNode->numara)!=0){
			gecici.InsertNode(newNode->ad,newNode->soyad,newNode->numara,newNode->dersAlis,newNode->yandalciftdal);
		}
		newNode=newNode->next;
	}
	int pindex=2,iindex=0;
	while(pindex>1){      
		i=gecici.head;
		while(i!=NULL){
			pivot=i; 
			newpivot=i; 
			ensag=i;       
			i=i->next;
			pindex++;
		}
		for(i=gecici.head,iindex=0;iindex<pindex;i=i->next,iindex++){ 
			if(newpivot->soyad < i->soyad){  
				if(newpivot->back==i){    
			 		temp=i;
			 		i=pivot;
			 		newpivot=i;
			 		pivot=temp;
			 		pindex--;
				}                                           
				else{          
					temp=i;
					i=pivot->back;
					pivot->back=pivot;
			   		newpivot=pivot->back;
					pivot=temp;
					pindex--;
				}
			}
		}
		if(newpivot->next!=NULL) ensag=newpivot->next;
		else ensag=newpivot;
		yazdir.InsertNode(ensag->ad,ensag->soyad,ensag->numara,ensag->dersAlis,ensag->yandalciftdal);
		gecici.DeleteNode(ensag->numara);
	}
	yazdir.DisplayList();
}

void RadixSort(){
	VeriList radixlist;
	DoublyNodeOther* doublyOtherNode=vlist.head;
	while(doublyOtherNode!=NULL){
		radixlist.InsertNode(doublyOtherNode->ad,doublyOtherNode->soyad,doublyOtherNode->numara,doublyOtherNode->dersAlis,doublyOtherNode->yandalciftdal);
		doublyOtherNode=doublyOtherNode->next;
	}
	DoublyNodeOther *i,*j, *enkucuk,*radixNode=radixlist.head;
	int max=0;
    while(radixNode != NULL){	
        if(radixNode->ad.length()>max) max=radixNode->ad.length();
		radixNode=radixNode->next;
    }
    for(int m=0; m<max;m++){
		for (i=radixlist.head; i!=NULL; i=i->next){
			enkucuk=i;
			DoublyNodeOther* jileri=NULL;
			DoublyNodeOther* jgeri=NULL;
			DoublyNodeOther* gecicij=NULL;
			DoublyNodeOther* igeri=NULL;
			for(j=i->next;j!=NULL; j=j->next){
				string bir;
				string iki;
				if(j->ad.length()<=max-1-m) bir="a";
				else bir=j->ad.substr(max-1-m,1);
				if(enkucuk->ad.length()<max-1-m) iki="a";
				else iki=enkucuk->ad.substr(max-1-m,1);
				if(bir<iki)	{
					enkucuk=j;
					gecicij=j;
				}
			}
			if(gecicij!=NULL){
				jileri=gecicij->next;
				jgeri=gecicij->back;
				jgeri->next=jileri;
				if(jileri!=0) jileri->back=jgeri;
				igeri=i->back;
				if(igeri!=0) igeri->next=gecicij;
				gecicij->back=igeri;
				gecicij->next=i;
				i->back=gecicij;
				if(gecicij->back==0) radixlist.head=gecicij;
				i=i->back;
			}
		}
		radixNode=radixlist.head;
		while(radixNode!=NULL){
			cout <<"Adi: " <<radixNode->ad<<" Soyadi: " <<radixNode->soyad<<" Numarasi: " <<radixNode->numara<<endl;
			radixNode=radixNode->next;
		}
		cout<<"-----------------------------------"<<endl;
	}
}

ProgramlamaList kumeleme;
void heapify(int n, int i){
    int largest = i;  
    int l = 2*i + 1;  
    int r = 2*i + 2;  
    DoublyNode* j;
    DoublyNode* temp;
    int m=0;
	for(j=kumeleme.head;j!=NULL;j=j->next){
		if(m==largest) temp=j;
		m++;		
	}	
    DoublyNode* temp2;
    int y=0;
	for(j=kumeleme.head;j!=NULL;j=j->next){
		if(y==l) temp2=j;
		y++;	
	}	
    DoublyNode* temp3;
    int q=0;
	for(j=kumeleme.head;j!=NULL;j=j->next){
		if(q==r) temp3=j;
		q++;	
	}	
    DoublyNode* temp4;
    int a=0;
	for(j=kumeleme.head;j!=NULL;j=j->next){
		if(a==i) temp4=j;
		a++;		
	}	
    if (l < n && temp2->numara > temp->numara) largest = l;
    m=0;
	for(j=kumeleme.head;j!=NULL;j=j->next){
		if(m==largest) temp=j;
		m++;		
	}
    if (r < n && temp3->numara > temp->numara) largest = r;
    m=0;
	for(j=kumeleme.head;j!=NULL;j=j->next){
		if(m==largest) temp=j;
		m++;	
	}
    if (largest == r){
    	swap(temp4->ad,temp3->ad);
 		  swap(temp4->soyad,temp3->soyad);
 		  swap(temp4->numara,temp3->numara);
 		  swap(temp4->dersAlis,temp3->dersAlis);
 		  swap(temp4->yandalciftdal,temp3->yandalciftdal);
      heapify(n, largest);
    }
    if (largest == l){
    	swap(temp4->ad,temp2->ad);
 		  swap(temp4->soyad,temp2->soyad);
 		  swap(temp4->numara,temp2->numara);
 		  swap(temp4->dersAlis,temp2->dersAlis);
 		  swap(temp4->yandalciftdal,temp2->yandalciftdal);
      heapify(n,largest);
    }
}

void  heapSort(){
	int sayac=0;
    DoublyNode* current=plist.head;
    while(current != NULL){
       	kumeleme.InsertNode(current->ad,current->soyad,current->numara,current->dersAlis,current->yandalciftdal);
        sayac++;  
        current = current -> next;
    }
    for (int w=(sayac/2)-1;w>=0;w--){
    	 heapify(sayac,w);
	}
    for (int o=sayac-1;o>=0;o--){
    	DoublyNode* j;
    	DoublyNode* temp;
    	int m=0;
		for(j=kumeleme.head;j!=NULL;j=j->next){
			if(m==o) temp=j;
			m++;
		}
        swap(kumeleme.head->ad,temp->ad);
        swap(kumeleme.head->soyad,temp->soyad);
        swap(kumeleme.head->numara,temp->numara);
        swap(kumeleme.head->dersAlis,temp->dersAlis);
        swap(kumeleme.head->yandalciftdal,temp->yandalciftdal);
        heapify(o,0);
    }
    kumeleme.DisplayList();
}

void ogrenciEkle(){
	plist.InsertNode("bahriye","kilic",103040442,1,0);
	plist.InsertNode("mahmut","arslan",1030520795,1,1);
	plist.InsertNode("berat","ilgaz",1030520775,1,0);
	plist.InsertNode("firat","yilmaz",1030375566,3,1);
	plist.InsertNode("akin","gul",1030520595,1,1);
	plist.InsertNode("kemal","yurt",1030522245,1,1);
	plist.InsertNode("mustafa","mango",1030378523,1,1);
	plist.InsertNode("yusuf","koc",1030373611,2,0);
	plist.InsertNode("oguz","aslan",1030373681,1,1);
	plist.InsertNode("burak","halk",1030378462,1,0);
	plist.InsertNode("esra","uray",1030376788,2,2);
	plist.InsertNode("kubra","vekil",1030374566,1,1);
	plist.InsertNode("yeliz","liman",1030378843,2,0);
	plist.InsertNode("faruk","abali",1030377647,1,1);
	plist.InsertNode("murat","yılmaz",1030374422,2,1);
	plist.InsertNode("hekim","turan",1030374729,1,0);
	plist.InsertNode("safa","serpil",1030378577,2,1);
	plist.InsertNode("fahriye","makas",1030378553,1,1);
	vlist.InsertNode("alper","polat",1030405226,1,1);
	vlist.InsertNode("bahriye","kilic",103040442,2,0);
	vlist.InsertNode("firat","yilmaz",1030375566,1,1);
	vlist.InsertNode("yusuf","koc",1030373611,2,0);
	vlist.InsertNode("dervis","karaboga",10307684,1,0);
	vlist.InsertNode("mustafa","mango",1030378523,1,1);
	vlist.InsertNode("aysenur","vekil",10304099,2,0);
	vlist.InsertNode("oguz","aslan",1030373681,2,1);
	vlist.InsertNode("mahmut","arslan",1030520795,2,1);
	vlist.InsertNode("bahar","yesil",1030406643,2,0);
	vlist.InsertNode("leyla","polat",1030490784,1,0);
	vlist.InsertNode("arif","ozturk",103040599,1,1);
	vlist.InsertNode("alperen","farya",1030404682,2,0);
	vlist.InsertNode("jale","zeynep",103040577,1,0);
	vlist.InsertNode("zeynep","ozturk",103040544,2,1);
	vlist.InsertNode("mirac","cem",103040526,3,0);
	vlist.InsertNode("onat","vezir",103040571,1,0);
	vlist.InsertNode("tugrul","selman",103040522,2,1);
}

int main(){
	ogrenciEkle();          
  int secim;
	while(secim!=-1){
	cout<<"***********************************************************"<<endl;
		cout<<"1)Bilgisayar Programlama Dersi temel islemleri icin"<<endl;
		cout<<"2)Veritabani Yonetim Sistemleri Dersi temel islemleri icin"<<endl;
		cout<<"3)Her iki derside birden fazla kez alan ogrencileri listemelemek icin"<<endl;
		cout<<"4)Sadece bilgisayar programlama dersini alan ogrencileri listelemek icin"<<endl;
		cout<<"5)Bilgisayar Programlama dersinin A ve B gruplarini listelemek icin"<<endl;
		cout<<"6)Veritabani Yonetim Sitemleri dersinin A ve B gruplarini listelemek icin"<<endl;
		cout<<"7)Her iki derside alan ve baska bolum ogrencileri olan ogrencileri listelemek icin"<<endl;
		cout<<"8)Hizli Siralama ile her iki derside alan ogrencileri soyadlarina gore siralayiniz"<<endl;
		cout<<"9)Radix Siralama ile Veritabani Yonetim Sistemleri dersini alan ogrencileri adlarina gore siralayiniz"<<endl;
		cout<<"10)Kumeleme Siralama ile Bilgisayar Programlama dersini alan ogrencileri numaralarina gore siralayiniz"<<endl;
		cout<<"Cikmak icin -1 giriniz"<<endl;
	cout<<"***********************************************************"<<endl;
		cin>>secim;
		if(secim==1){
			int psecim;
			cout<<"1)Ogrenci eklemek icin"<<endl;
			cout<<"2)Ogrenci bulmak icin"<<endl;
			cout<<"3)Ogrenci silmek icin"<<endl;
			cout<<"4)Sinif listesini gormek icin"<<endl;
			cin>>psecim;
			if(psecim==1){
				string ad,soyad;
				int no,alis,dal;
				cout<<"Sirasiyla ogrencinin adini,soyadini,numarasini,"<<endl<<"dersi kacinci kez aldigini ve yandal veya cift dal durumu varsa 1 yoksa 0 giriniz..."<<endl;
				cin>>ad>>soyad>>no>>alis>>dal;
				plist.InsertNode(ad,soyad,no,alis,dal);
				cout<<"Ekleme basarili..."<<endl;
			}
			else if(psecim==2){
				int numara;
				cout<<"Aranan ogrencinin numarasini giriniz ="<<endl;
				cin>>numara;
				if(plist.FindNode(numara)!=0) cout<<"Ogrenci bulunmustur..."<<endl;
				else cout<<"Ogrenci bulunamamistir..."<<endl;
			}  
			else if(psecim==3){
				int numara;
				cout<<"Silinecek ogrencinin numarasini giriniz ="<<endl;
				cin>>numara;
				if(plist.DeleteNode(numara)!=0) cout<<"Ogrenci silinmistir..."<<endl;
				else cout<<"Ogrenci bulunamamistir"<<endl;
			}
			else if(psecim==4){
				plist.DisplayList();
			}
			else cout<<"Gecerli bir secim yapmadiniz !!!"<<endl;
		}
		else if(secim==2){
			int vsecim;
			cout<<"1)Ogrenci eklemek icin"<<endl;
			cout<<"2)Ogrenci bulmak icin"<<endl;
			cout<<"3)Ogrenci silmek icin"<<endl;
			cout<<"4)Sinif listesini gormek icin"<<endl;
			cin>>vsecim;
			if(vsecim==1){
				string ad,soyad;
				int no,alis,dal;
				cout<<"Sirasiyla ogrencinin adini,soyadini,numarasini,"<<endl<<"dersi kacinci kez aldigini ve yandal veya cift dal durumu varsa 1 yoksa 0 giriniz..."<<endl;
				cin>>ad>>soyad>>no>>alis>>dal;
				vlist.InsertNode(ad,soyad,no,alis,dal);
				cout<<"Ekleme basarili..."<<endl;
			}
			else if(vsecim==2){
				int numara;
				cout<<"Aranan ogrencinin numarasini giriniz ="<<endl;
				cin>>numara;
				if(vlist.FindNode(numara)!=0) cout<<"Ogrenci bulunmustur..."<<endl;
				else cout<<"Ogrenci bulunamamistir..."<<endl;
			}  
			else if(vsecim==3){
				int numara;
				cout<<"Silinecek ogrencinin numarasini giriniz ="<<endl;
				cin>>numara;
				if(vlist.DeleteNode(numara)!=0) cout<<"Ogrenci silinmistir..."<<endl;
				else cout<<"Ogrenci bulunamamistir"<<endl;
			}
			else if(vsecim==4){
				vlist.DisplayList();
			}
			else cout<<"Gecerli bir secim yapmadiniz !!!"<<endl;
		}
		else if(secim==3){
			plist.DigerListeleme1();
			vlist.DigerListeleme1();
		}
		else if(secim==4) plist.DigerListeleme2();
		else if(secim==5) plist.DigerListeleme3();
		else if(secim==6) vlist.DigerListeleme4();
		else if(secim==7) plist.DigerListeleme5();
		else if(secim==8) HizliSiralama();
		else if(secim==9) RadixSort();
		else if(secim==10) heapSort();
		else cout<<"Gecerli bir secim yapmadiniz !!!"<<endl;
	}    return 0;
}
