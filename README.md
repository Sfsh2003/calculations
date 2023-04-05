#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Struct for storing contact information
struct Contact {
    char name[50];
    char email[50];
    char phone[15];
};

int main() {
    struct Contact contacts[50]; // Maximum 50 contacts can be stored
    int numContacts = 0; // Number of contacts currently stored

    while (1) {
        printf("\nContact Management Studio\n");
        printf("1. Add Contact\n");
        printf("2. View Contacts\n");
        printf("3. Exit\n");
        printf("Enter choice: ");
        
        int choice;
        scanf("%d", &choice);

        if (choice == 1) {
            if (numContacts == 50) {
                printf("Error: Maximum number of contacts reached.\n");
                continue;
            }
            
            printf("\nEnter name: ");
            scanf("%s", contacts[numContacts].name);

            printf("Enter email: ");
            scanf("%s", contacts[numContacts].email);

            printf("Enter phone: ");
            scanf("%s", contacts[numContacts].phone);

            printf("\nContact added successfully.\n");
            numContacts++;
        } 
        else if (choice == 2) {
            printf("\nList of Contacts:\n");

            for (int i = 0; i < numContacts; i++) {
                printf("\n%d. Name: %s\n", i+1, contacts[i].name);
                printf("   Email: %s\n", contacts[i].email);
                printf("   Phone: %s\n", contacts[i].phone);
            }

            if (numContacts == 0) {
                printf("\nNo contacts found.\n");
            }
        } 
        else if (choice == 3) {
            printf("\nExiting Contact Management Studio...\n");
            break;
        } 
        else {
            printf("\nInvalid choice. Please enter a valid choice.\n");
        }
    }

    return 0;
}