# Data-structure-through-python linked list 
#create node
#create linked list
#Add nodes to linked list
#print linked list
class Node: #okk
    def __init__(self,data):
        self.data=data
        self.next=None #okk
class Linkedlist:
    def __init__(self):
        self.head=None #okk
    def inserthead(self, newnode):
        temporarynode=self.head
        self.head=newnode
        self.head.next=temporarynode
        del temporarynode #okk
    def listlength(self):
        currentnode=self.head
        length=0
        while currentnode is not None:
            length+=1
            currentnode=currentnode.next
        return length    #okk

    def insertat(self,newnode,position):
        if position<0 or position> self.listlength():
            print("Invalid position")
        elif position==0:
            self.inserthead(newnode)
            
        else:
            currentnode=self.head
            currentposition=0
            while True:
                if currentposition==position:
                      previousnode.next=newnode
                      newnode.next=currentnode
                      break
                previousnode=currentnode
                currentnode=currentnode.next
                currentposition+=1
                #okk

        
    def insert(self,newnode):
        if self.head is None:
            self.head=newnode
        else:
            lastnode=self.head
            while True:
                if lastnode.next is None:
                    break
                lastnode=lastnode.next
            lastnode.next=newnode #okk
    def islistempty(self):
        if self.head is None:
            return True
        else:
            return False #okk
    def deletehead(self):
        if self.islistempty() is False:
            previousnode=self.head
            self.head=self.head.next
            previousnode.next=None
        else:
            print("Linked list is empty")
            
    def deleteat(self,position):
        if position<0 or position>= self.listlength():
            print("Invalid position")
            return
        if self.islistempty() is False:
            if position is 0:
                self.deletehead()
                return 
            currentnode=self.head
            currentposition=0
            while True:
                if currentposition==position:
                     previousnode.next=currentnode.next
                     currentnode.next=None
                     break
                previousnode=currentnode
                currentnode=currentnode.next
                currentposition+=1
        else:
            print("list is empty")
    def deleteend(self):
        lastnode=self.head
        while lastnode.next is not None:
            previoudnode=lastnode
            lastnode=lastnode.next    
        del lastnode
        previoudnode.next=None    
    def printlist(self):
        if self.head==None:
            print("list is empty")
        currentnode=self.head
        while True:
            if currentnode is None:
                break
            #return
            print(currentnode.data)
            currentnode=currentnode.next
firstnode=Node("Ashish")            
linkedlist=Linkedlist()
linkedlist.islistempty()
linkedlist.inserthead(firstnode)
secondnode=Node("Sanoo")
linkedlist.inserthead(secondnode)
thirdnode=Node("Sheelu")
linkedlist.insert(thirdnode)
fourthnode=Node("Kirti")
linkedlist.insertat(fourthnode,3)
linkedlist.printlist()
print("=====deleting node from the head =====")
linkedlist.deletehead()
linkedlist.printlist()
print("====deleting from the position====")
linkedlist.deleteat(2)
linkedlist.printlist()
print("====deleting from the end====")
linkedlist.deleteend()
linkedlist.printlist()

# output 
Sanoo
Ashish
Sheelu
Kirti
=====deleting node from the head =====
Ashish
Sheelu
Kirti
====deleting from the position====
Ashish
Sheelu
====deleting from the end====
Ashish
