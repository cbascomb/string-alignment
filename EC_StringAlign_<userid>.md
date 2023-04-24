#include <iostream>
#include <iomanip>
#include <string>
using namespace std;

int main()
{
	// declare variables
	string text;
	int width,len, left_padding,right_padding;

	//read input
	cout << "Enter a string to align: ";

	//read string, string may contain spaces, so use getline
	getline(cin, text);

	//read width
	cout << "Enter a width for alignment: ";
	cin >> width;
	
	//display symbols for visual clearness
	cout << endl;
	for (int i = 0; i < width; i++) cout << "#";
	cout << endl;

	//get the length of the text
	len = text.length();

	//if widths is less than or equal to length, just display text
	if (width <= len)
	{
		cout << text << endl;
	}
	//otherwise align it
	else
	{
		//calculate left and right padding
		left_padding = (width - len) / 2;
		right_padding = width - len- left_padding;

		//display padding number of spaces, then display the text
		cout << setfill(' ') << setw(left_padding) << "" 
			<< text << setfill(' ') << setw(right_padding) << "" << endl;
	}


	return 0;
}
