# singly-linked-list-DSA
class Node{
    int data;
    Node next;
    
    Node(int data){
        this.data = data;
        this.next = null;
    }
}

class SinglyLinkedList{
    // insert at begin
    
     Node head;
    
    public void InsertAtBegin(int data){
        Node newNode = new Node(data);
            newNode.next = head;
            head= newNode;
    }
// Insert at end
public void InsertAtEnd(int data){
    Node newNode=new Node(data);
    Node temp=head;
    while(temp.next!=null){
        temp=temp.next;
    }
    temp.next=newNode;
}
  // insert at any position
  
  public void InsertAtAnyPosition(int position, int data){
       
        if(position<=0){
            System.out.println("Invalid Position");
            return;
        }
        
        Node newNode = new Node(data);
        
        if(position==1){
            newNode.next = head;
            head= newNode;
            return;
        }
         
         Node temp = head;
         
        for(int i=0;i<position-1 && temp !=null; i++){
          temp = temp.next;
        }
        
        if(temp==null){
            System.out.println("Exceeds the given length");
            return;
        }
        
        newNode.next = temp.next;
        temp.next = newNode;
  }
//   deleteatbegin
public void deleteAtBegin(){
    if(head==null){
        System.out.println("no node delete");
        return;
    }
    head=head.next;
}
  
  //delete at end 
  
  public void deleteAtend(){
      
      if(head==null){
          System.out.println("list is empty, no need to delete");
          return;
      }
      
      if(head.next==null){
          head=null;
          return;
      }
      
      Node temp = head;
      
      while(temp.next != null && temp.next.next!=null){
          temp = temp.next;
      }
      temp.next=null;
  }
  
  
    public void display(){
        Node temp = head;
        while(temp != null){
            System.out.print(temp.data + " ");
            temp = temp.next;
    }
    
    System.out.println();
    
}

}


public class Main{
    public static void main(String[] args){
        SinglyLinkedList list = new SinglyLinkedList();
        System.out.println("InsertAtBegin");
        list.InsertAtBegin(10);
        list.InsertAtBegin(20);
        list.InsertAtBegin(30);
        list.InsertAtBegin(40);
        list.InsertAtBegin(50);
         list.display();
         System.out.println("InsertAtEnd");
        list.InsertAtEnd(23);
        list.InsertAtEnd(20);
        list.InsertAtEnd(30);
        list.InsertAtEnd(40);
        list.InsertAtEnd(90);
        list.display();
        System.out.println("InsertAtAnyPosition");
        
        list.InsertAtAnyPosition(3,150);
        list.display();
        System.out.println("deleteAtBegin");
        list.deleteAtBegin();
        list.display();
        System.out.println("deleteAtend");
        list.deleteAtend();
        list.display();
    }
}

OUTPUT
