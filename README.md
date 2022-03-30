#include <iostream>
#include <Windows.h>
using namespace std;

int main() {
	cout << "UPDOWN 게임에 오신 여러분 환영합니다! 바로 게임을 시작하도록 하겠습니다~ \n";
	Sleep(1000);
	cout << "컴퓨터가 랜덤으로 0부터 50 까지의 숫자 중 하나를 정하는 중입니다.";
	Sleep(700);
	cout << ".";
	Sleep(700);
	cout << ".";
	Sleep(700);
	cout << ".\n";

	srand((unsigned int)time(NULL));
	int random = rand() % 51;

	cout << "컴퓨터가 숫자를 설정했습니다.\n\n";

	for (int i = 0; i < 7; i++) {
		cout << "1부터 50까지의 숫자중 하나를 입력해주세요!: ";
		int num;
		cin >> num;

		if (num < 0 || num>50) {
			cout << "1미만, 50 초과 숫자는 입력하실 수 없습니다.\n 패널티로 기회 1번을 소모합니다.\n";
			continue;
		}

		if (num == random) {
			cout << "정답입니다!\n\n"<< i + 1 << "번째 시도에서 성공하셨습니다!\n";
			return 0;

		}

		if (num < random) {
			cout << "UP\n";
		}
		else if(num>random) {
			cout << "DOWN\n";
		}

	}
	cout << "7번의 기회를 모두 소모하여 패배했습니다.\n\n";
	cout << "정답은 바로바로...";
	Sleep(1000);

	cout << random << " 이었습니다! 더 노력하시길 바래요~\n";

}
