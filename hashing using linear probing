#include <stdio.h>
#include <stdlib.h>

#define SIZE 10 // Size of the hash table

struct HashTable {
    int *array;
    int capacity;
};

struct HashTable* createHashTable(int capacity) {
    struct HashTable *hashTable = (struct HashTable*)malloc(sizeof(struct HashTable));
    hashTable->capacity = capacity;
    hashTable->array = (int*)malloc(sizeof(int) * capacity);
    for (int i = 0; i < capacity; i++) {
        hashTable->array[i] = -1; // Initialize all slots as empty (-1)
    }
    return hashTable;
}

int hashFunction(int key, int capacity) {
    return key % capacity;
}

void insert(struct HashTable *hashTable, int key) {
    int index = hashFunction(key, hashTable->capacity);

    while (hashTable->array[index] != -1) {
        index = (index + 1) % hashTable->capacity; // Linear probing
    }

    hashTable->array[index] = key;
}

void display(struct HashTable *hashTable) {
    printf("Hash Table:\n");
    for (int i = 0; i < hashTable->capacity; i++) {
        printf("%d: %d\n", i, hashTable->array[i]);
    }
}

int main() {
    struct HashTable *hashTable = createHashTable(SIZE);

    insert(hashTable, 5);
    insert(hashTable, 15);
    insert(hashTable, 25);
    insert(hashTable, 12);
    insert(hashTable, 22);

    display(hashTable);

    free(hashTable->array);
    free(hashTable);

    return 0;
}
