# Data-Structure-Chinese-Translation
This repository recorded the chinese translation for corresponding data structure terms. Sample code for some data structures are written in C++. 
Linked list 链表
Pointer 指标
Array 阵列






Stack 栈
Queue 队列
Deques 双端队列
Priority Queue 优先队列
List 串列
Binary Tree 二元树
Search Tree 查找树
Heaps 堆
Hash Table 哈希表
Maps 关联容器
Set(STL)
Graph(STL) 图






Constructor 构建函数
Destructor 析构函数 ~Destructor{ delete[] arr; }
Sort 排序
Dynamic Programming 动态规划
String 字串






Singly Linked List
class StringNode {
private:
	string elem;
	StringNode* next;

	friend class StringLinkedList;
};

class StringLinked List {
public:
	StringLinkedList();
	~StringLinkedList();
	bool empty() const;
	const string& front const;
	void addFront(const string& e);
	void removeFront();

private:
	StringNode* Head;
};

void StringLinked::addFront(const string& e) {
	StringNode* v = new StringNode;
	v->elem = e;
	v->next = head;
	head = v;
}

void removeFront() {
	StringNode* old = head;
	head = old->next;
	delete old;
}






Doubly Linked Lists
typedef string Elem;
class DNode {
private:
	Elem elem;
	DNode* next;
	DNode* prev;
	friend class DLinkedList;
};

class DLinkedList {
public:
	DLinkedList();
	~DLinkedList();
	bool empty() const;
	const Elem& front() const;
	const Elem& back() const;
	void addFront(const Elem& e);
	void addBack(const Elem& e);
	void removeFront();
	void removeBack();
private:
	DNode* header;
	DNode* trailer;
protected:
	void add(DNode* v, const Elem& e); // add before v
	void remove(DNode* v);
};

DLinkedList::DLinkedList() {
	header = new DNode;
	trailer = new DNode;
	header->next = trailer;
	trailer->prev = header;
}

void DLinkedList::add(DNode* v, const Elem& e) {
	DNode* u = new DNode;
	u->elem = e;
	u->next = v;
	u->prev = v->prev;
	v->prev->next = v->prev = u;
}

void DLinkedList::addFront(const Elem& e) {
	add(header->next, e);
}

void DLinkedList::addBack(const Elem& e) {
	add(Trailer, e);
}

void DLinkedList::remove(DNode* v) {
	DNode* u = v->prev;
	DNode* w = v->next;
	u->next = w;
	w->prev = u;
	/* v->prev->next = v->next;
	v->next->prev = v->prev; */
	delete v;
}

void DLinkedList::removeFront() {
	remove(header->next);
}

void DLinkedList::removeBack() {
	remove(trailer->prev);
}






template <typename T>
T  genericMin(T a, T b) {
	return (a < b ? a ： b);
}






Throw and Catch
if (divisor == 0)
throw ZeroDivide("Divide by zero");

catch (ZeroDivide& zde) {//handle division by zero}






	Array Insertion
		void add(const GameEntry& e) {
		int newScore = e.getScore();

		int i = numEntries - 2;
		while (i >= 0 && newScore > entries[i].getScore()) {
			entries[i + 1] = entries[i];
			i--;
		}
		entries[i + 1] = e;
	}






	Array Removel
		void remove(int i) throw(IndexOutOfBounds) {
		GameEntry e = entries[i];
		for (int j = i + 1； j < numEntries; j++)
			entries[j - 1] = entries[j];
		numEntries--;
		return;
	}






	Array Insertion Sort
		void insertionSort(char* A, int n) {
		for (i = 1; i < n; i++) {
			char current = A[i];
			int j = i - 1;
			if (j >= 0 && A[j] > current) {
				A[j + 1] = A[j];
				j--;
			}
			A[j + 1] = current;
		}
	}






	Dynamic memory
		int foo*
		foo = new int[5];

access: foo[1] or *(foo + 1)






	MAP STL
#include <map>
	map<int, string> mapStudent;
		mapStdent.insert(pair<int, string>(1, "student_one"));
		map<int, string>::iterator iter;
		for (iter = mapStudent.begin(); iter != mapStudent.end(); iter++) {
			cout << iter->first << " " << iter->second << end;
		}






		Matrices STL using vector
			n X m Matrices :
		vector< vector<int> > M(n, vector<int>(m));
		cout << M[i][j] << endl;
