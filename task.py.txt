class Graph:
 
    def init(self, vertices):
        self.V = vertices  
        self.graph = []
        
 
    def addEdge(self, u, v, w):
        self.graph.append([u, v, w])
 

    def find(self, parent, i):
        if parent[i] != i:

            parent[i] = self.find(parent, parent[i])
        return parent[i]
 

    def union(self, parent, rank, x, y):
        
        if rank[x] < rank[y]:
            parent[x] = y
        elif rank[x] > rank[y]:
            parent[y] = x
 

        else:
            parent[y] = x
            rank[x] += 1
 

    def KruskalMST(self):
 
        result = []  

        i = 0
 
        e = 0
 

        self.graph = sorted(self.graph,
                            key=lambda item: item[2])
 
        parent = []
        rank …
Python program for implementation of MergeSort
def mergeSort(arr):
    if len(arr) > 1:
 

        mid = len(arr)//2
 
        L = arr[:mid]
 

        R = arr[mid:]
 

        mergeSort(L)
 

        mergeSort(R)
 
        i = j = k = 0
 

        while i < len(L) and j < len(R):
            if L[i] <= R[j]:
                arr[k] = L[i]
                i += 1
            else:
                arr[k] = R[j]
                j += 1
            k += 1
 
        while i < len(L):
            arr[k] = L[i]
            i += 1
            k += 1
 
        while j < len(R):
            arr[k] = R[j]
            j += 1
            k += 1
 

 
 
def printList(arr):
    for i in range(len(arr)):
        print(arr[i], end=" ")
    print()
 
 

if name == 'main':
    arr = [12, 11, 13, 5, 6, 7]
    print("Given array is", end="\n")
    printList(arr)
    mergeSort(arr)
    print("Sorted array is: ", end="\n")
    printList(arr)