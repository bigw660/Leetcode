# Disjoint-set (or Union-Find)
class UF:
    def __init__(self, n):
        self.parent = [i for i in range(n)]
        self.size = [1] * n
        
    def isConnected(self, a, b):
        return self.find(a) == self.find(b)
    
    def find(self, a):
        while self.parent[a] != a:            
            # path compression
            self.parent[a] = self.parent[self.parent[a]]
            a = self.parent[a]
        return a
    
    def union(self, a, b):
        p1 = self.find(a)
        p2 = self.find(b)
        if self.isConnected(p1, p2):
            return
        
        # optimization - try to make the new tree balanced
        if self.size[p1] < self.size[p2]:
            self.parent[p1] = p2
            self.size[p2] += self.size[p1]
        else:
            self.parent[p2] = p1
            self.size[p1] += self.size[p2]
