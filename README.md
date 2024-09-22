# c-![image](https://github.com/user-attachments/assets/aa7f7a5e-516f-4ada-9d19-620f201180f0)
#include <iostream>
#include <string>
#include <ctime>
using namespace std;

struct student {
	string name;
	int score;
};

struct teacher {
	string Name;
	student stu[5];
};

void allocateSpace (teacher tArr[]) {

	string nameSeed = "ABCDE";

	for (int i = 0; i < 3; i++) {
		tArr[i].Name = "teacher_";
		tArr[i].Name += nameSeed[i];
		for (int j = 0; j < 5; j++) {
			tArr[i].stu[j].name = "student_";
			tArr[i].stu[j].name += nameSeed[j];
			tArr[i].stu[j].score = rand() % 61 + 40;
		}
	}
}

void printArray(teacher tArr[]) {
	for (int i = 0; i < 3; i++) {
		cout << "老师名字是："<<tArr[i].Name << endl;
		for (int j = 0; j < 5; j++) {
			cout << "学生名字是：" << tArr[i].stu[j].name << "  得分为：" << tArr[i].stu[j].score << endl;
		}
	}
}

int main() {
	srand((unsigned int)time(NULL));

	teacher tArr[3];
	allocateSpace(tArr);
	
	printArray(tArr);

	return 0;
}
