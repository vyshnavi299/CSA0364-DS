#include <stdio.h>
#include <stdlib.h>

struct Node {
    int key;
    struct Node* left;
    struct Node* right;
    int height;
};

int max(int a, int b) {
    return (a > b) ? a : b;
}

int height(struct Node* node) {
    if (node == NULL)
        return 0;
    return node->height;
}

struct Node* newNode(int key) {
    struct Node* node = (struct Node*)malloc(sizeof(struct Node));
    node->key = key;
    node->left = NULL;
    node->right = NULL;
    node->height = 1;
    return node;
}

int search(struct Node* root, int key) {
    if (root == NULL)
        return 0;

    if (key < root->key)
        return search(root->left, key);
    else if (key > root->key)
        return search(root->right, key);
    else
        return 1;
}

int main() {
    struct Node* root = NULL;

    int n, key;
    printf("Enter the number of elements: ");
    scanf("%d", &n);

    printf("Enter the elements:\n");
    for (int i = 0; i < n; i++) {
        scanf("%d", &key);
        root = insert(root, key);
    }

    printf("Enter the element to search for: ");
    scanf("%d", &key);

    if (search(root, key))
        printf("Element %d found in the AVL tree.\n", key);
    else
        printf("Element %d not found in the AVL tree.\n", key);

    return 0;
}
