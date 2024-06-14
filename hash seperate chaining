#include <stdio.h>
#include <stdlib.h>
#define SIZE 10
struct node {
   int data;
   struct node *next;
};
void initialize(struct node **table) {
   int i;
   for (i = 0; i < SIZE; i++) {
    table[i] = NULL;
   }
}
int hash(int key) {
   return key % SIZE;
}
void insert(struct node **table, int key) {
   int index = hash(key);
   struct node *new_node = (struct node *)malloc(sizeof(struct node));
   new_node->data = key;
   new_node->next = NULL;
   if (table[index] == NULL) {
    table[index] = new_node;
   } else {
    struct node *temp = table[index];
    while (temp->next != NULL) {
    temp = temp->next;
    }
    temp->next = new_node;
   }
}
void display(struct node **table) {
   int i;
   for (i = 0; i < SIZE; i++) {
    printf("[%d] -> ", i);
    struct node *temp = table[i];
    while (temp != NULL) {
    printf("%d -> ", temp->data);
    temp = temp->next;
    }
    printf("NULL\n");
   }
}
int main() {
   struct node *hash_table[SIZE];
   initialize(hash_table);
   insert(hash_table, 51);
   insert(hash_table, 15);
   insert(hash_table, 25);
   insert(hash_table, 36);
   insert(hash_table, 18);
   insert(hash_table, 16);
   insert(hash_table, 27);
   insert(hash_table, 33);
   display(hash_table);
   return 0;
}
