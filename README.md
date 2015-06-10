#include<iostream>
#include<string>
using namespace std;
template <class T>
class ListIterator;
template<class T>
class List
{
	friend class ListIterator<T>; //declaration of <Template>class iterator 

public:
	List(int size);
	~List(){ delete [] listArray; }

	bool isFull() { return mSize == MaxSize; }
	bool isEmpty() { return mSize == 0; }
	int length() { return mSize; }
	void insert(const T value);
	bool remove(const T value);
	void setData(int index, T value);
	T getData(int index);
	int search(T key);
	List(const List & other);//copy constructor
	const List& operator=(const List & rhs);  //assignment operator

private:
	bool removeAt(int index);
	int MaxSize;
	int mSize;
	T *listArray;

};
template<class T>
List<T>::List(int size)
{
	if (size < 1)  throw  "ILLEGAL_SIZE";
	else{ MaxSize = size;
	listArray = new T[MaxSize];
	if (listArray == NULL) throw "OUT_OF_MEMORY";

	mSize = 0;
	}
}

template<class T>
void List<T>::insert(const T value)
{
	if (isFull()) throw "OUT_OF_SPACE";
		listArray[mSize] = value;
		mSize++;
}

template<class T>
bool List<T>::remove(const T value)
{
	int index = search(value);
	if (index == -1) return false;
	else return removeAt(index);
}

template<class T>
bool List<T>::removeAt(int index)
{
	if (index < 0 || index >= mSize)
		throw "ILLEGAL_INDEX";
	else
	{
		listArray[index] = listArray[mSize - 1];
		mSize--;
		return true;
	}

}
template<class T>
T List<T>::getData(int index)
{
	if (index < 0 || index >= mSize) throw "ILLEGAL_INDEX";
	else	return listArray[index];
}

template<class T>
void List<T>::setData(int index, T value)
{
	if (index < 0 || index >= mSize) throw "ILLEGAL_INDEX";
	else	 listArray[index]=value;
}

template<class T>
int List<T>::search(T key)
{
	for (int i = 0; i < mSize;i++)
	if (listArray[i] == key) return i;

	return mSize;
}

template<class T>
List<T>::List(const List &other)
{ 
	other=&list;

}


template <class T>
class ListIterator {
private:
List<T> &list;
int current;
ListIterator & operator =(const ListIterator & rhs);
// disallow assignment
public:

ListIterator( List<T> &l): list(l) {current=0; }
ListIterator(const ListIterator<T> &li): list(li.list), current(li.current) { } // copy constructor

// overloaded assignment operator

void begin(){current = 0;}

void end() {current = list.mSize;}

bool isStart() {return current == 0;}

bool isDone() {return (current==list.mSize); }

void next() {

if (!isDone()) current++;

else throw "ILLEGAL_REFERNCE";

}


bool find(const T key) {

current = list.search(key);

if (!isDone()) return true; else return false;
}

T getData(){return list.listArray[current];}  // get data of the current element
void setData(const T value); // change value of the current element
};
template<class T>
void ListIterator<T>::setData(const T value){list.insert(value); current++;}


main()
{
	try{
	List<int> intList(10);

    ListIterator<int> myIterator(intList); // create iterator and
    //attach list to it
    int temp = 0;
	int x=0;
    for(int i=0;i<10;i++)
	{cout<<"Enter Data "<<i+1<<"#";
	  cin>>x;
	myIterator.setData(x);
	}
	
	myIterator.begin();
    while(!myIterator.isDone()) {         // temp now has sum of all elements

    temp = temp + myIterator.getData();
    myIterator.next();
	}
cout<<endl;


	cout<<"Sum="<<temp<<endl;

	}
	catch (char e[]){ cout << e << endl; }
	catch (...){  }
system("pause");
	return 0;
}
