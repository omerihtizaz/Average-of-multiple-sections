# Average-of-multiple-sections
# This program is made without using any arrays. 

#include <iostream> 
using namespace std;

int main () {
	
	int total_people = 0;
	int total_marks_combined = 0;
	int total_section = 0;
	int section_total_people = 0;
	int section_marks = 0;
	int marks;
	int section = 1;
	char choice;
	cout << "Please enter marks of students.\nAfter doing so enter -1" << endl;
	while (1)
	{
		while(1)
		{
			cout << "->";
			cin >> marks;
			if (marks  == -1)
			{
				cout << "Total marks of Section " << section << "= " << section_marks << endl;
				cout << "Total Number of Students in section " << section << "= " << section_total_people << endl;
				cout << "Average of Section "  << section <<  ": " << section_marks / section_total_people << endl;
				total_people += section_total_people;
				total_marks_combined += section_marks;
				section_marks = 0;
				section_total_people = 0;
				section++; 
				break;
			}
			cout<<endl;
			section_marks += marks;
			section_total_people++;
		}
		cout << "Do you want to enter another section's marks? [Y/N]" << endl;
		cin >> choice;
		if (choice == 'N' || choice == 'n')
		{
			cout << "Total number of students in all sections = " << total_people << endl;
			cout << "Total number of sections =" << section - 1 << endl;
			cout << "Total marks of all students combined = " << total_marks_combined << endl;
			cout << "Total Average of all sections = " << total_marks_combined / total_people << endl;
			break;
		}

	}
  return 0;
}
