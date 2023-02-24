# Tarea2-Colas

public class Cola {
    
    private NodoC frente;
    private NodoC ultimo;

   public void encola(String p) {
       NodoC n = new NodoC(p);
       if (frente==null) {
           frente=n;
           ultimo=frente;
       } else {           
           ultimo.setAtras(n);
           ultimo=n;
       }
   }
   public String atiende() {
       String p=null;
       if (frente!=null) {
           p=frente.getDato();
           frente=frente.getAtras();
           if (frente==null) {
               ultimo=null;
           }
       }
       return p;
   }
  
    public void imprime() {
        NodoC n = frente;
        while (n != null) {
            System.out.println(n.getDato());
            n = n.getAtras();
        }
    }

    @Override
    public String toString() {
        String s="";
        NodoC n = frente;
        while (n != null) {
            s+=n.getDato()+",";
            n = n.getAtras();
        }
        return s;
    }
}
