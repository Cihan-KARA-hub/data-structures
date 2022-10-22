# data-structures
/**
 *  çift yönlü bağlı listede:
 * - başa ve sona eleman ekleme
 * - baştan ve sondan eleman silme 
 * - yanyana tekrar eden elemanları silme
 * - elemanları listeleme
 *  
 */
class liste{
int data;
liste next;
liste back;

    public liste( int eleman) {
        this.data=eleman;
        next=null;
        back=null;
    }
}
public class sıralıBağlı {
    liste first;
    liste last;

    public sıralıBağlı() {
        first=null;
        last=null;
        
    }
    void sonaekle (liste eleman){
    if(first==null){
    first=eleman;
    last=eleman;
    }
    else{
    last.next=eleman;
    eleman.back=last;
    last=eleman;
    }
    }
    void başaEkle(liste eleman){
        
    if(first==null){
    first=eleman;
    last=eleman;
    }
    else{
    first.back=eleman;
    eleman.next=first;
    first=eleman;
    }
    }
    void sondanSil(){
    if(first==null){
        System.out.println(" liste boş...");
    }
    else{
    last.back.next=null;
    last.next=null;
    }
    }
    void baştanSil(){
    if(first==null){
        System.out.println("listede eleman yok...");
    }
    else {
    first=first.next;
    }
    }
    void tekrarıSil(){
        liste index=first;
        liste tut=null;
        
        if(first==null){
            System.out.println("liste boş");
        }
        else{
           while(index.next!=null){
               
              if(index.data==index.next.data){
                  if(index==first)
                  {
                  first=index.next;
                  }
                  else
                  {
                  index.back.next=index.next;
                  }
                  if(index==last){
                  index.back.next=null;
                  }
                  else
                  {
                  index.next.back=index.back;
                  }
           System.out.println(" tekrar eden eleman buldu : "+index.data);
              
              }
              
              
               index=index.next;
           }
        }
    
    }
     void listele(){
         liste index = first; int i =0;
     if(first==null){
         System.out.println(" liste boş...");
     }
     else {
         while(index!=null){
             System.out.println(i+" . eleman :"+ index.data);
             i++;
             index=index.next;
     }
     
     }
     }
    
}
