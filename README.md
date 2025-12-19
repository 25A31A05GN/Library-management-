# Library-management-
#A library management system in C is typically a console-based application that uses structures to represent books and file handling for persistent data storage.
#include <stdio.h>
#include <stdlib.h>

struct Book {
    int id;
    char title[50];
    char author[50];
};

int main() {
    struct Book library[100];
    int count = 0, choice;

    while (1) {
        printf("\n1. Add Book\n2. View Books\n3. Exit\nEnter choice: ");
        scanf("%d", &choice);

        if (choice == 1) {
            printf("Enter ID: ");
            scanf("%d", &library[count].id);
            printf("Enter Title: ");
            scanf("%s", library[count].title);
            printf("Enter Author: ");
            scanf("%s", library[count].author);
            count++;
        } else if (choice == 2) {
            for (int i = 0; i < count; i++) {
                printf("\nID: %d | Title: %s | Author: %s", 
                        library[i].id, library[i].title, library[i].author);
            }
        } else if (choice == 3) {
            exit(0);
        }
    }
    return 0;
}
