#include <stdio.h>
#include <stdlib.h>
#define SIZE 10
typedef struct {
    int key;
    int value;
} HashEntry;
typedef struct {
    HashEntry* table;
    int capacity;
} HashTable;
HashTable* createHashTable(int capacity) {
    HashTable* hashTable = (HashTable*)malloc(sizeof(HashTable));
    hashTable->table = (HashEntry*)malloc(capacity * sizeof(HashEntry));
    hashTable->capacity = capacity;
    for (int i = 0; i < capacity; i++) {
        hashTable->table[i].key = -1;
        hashTable->table[i].value = -1;
    }
    return hashTable;
}
int hash(int key) {
    return key % SIZE;
}
void insert(HashTable* hashTable, int key, int value) {
    int index = hash(key);
    while (hashTable->table[index].key != -1) {
        index = (index + 1) % SIZE;
    }
    hashTable->table[index].key = key;
    hashTable->table[index].value = value;
}
int search(HashTable* hashTable, int key) {
    int index = hash(key);
    while (hashTable->table[index].key != key) {
        index = (index + 1) % SIZE;
        if (hashTable->table[index].key == -1) {
            return -1;
        }
    }
    return hashTable->table[index].value;
}
void display(HashTable* hashTable) {
    for (int i = 0; i < SIZE; i++) {
        if (hashTable->table[i].key != -1) {
            printf("Key: %d, Value: %d\n", hashTable->table[i].key, hashTable->table[i].value);
        }
    }
}
int main() {
    HashTable* hashTable = createHashTable(SIZE);
    insert(hashTable, 5, 10);
    insert(hashTable, 15, 20);
    insert(hashTable, 25, 30);
    display(hashTable);
    int value = search(hashTable, 15);
    printf("Value: %d\n", value);
    return 0;
}
