# Tarea2-Colas

public class NodoC {
    private String dato;
    private NodoC atras;

    public NodoC getAtras() {
        return atras;
    }

    public void setAtras(NodoC atras) {
        this.atras = atras;
    }

    public String getDato() {
        return dato;
    }

    public void setDato(String dato) {
        this.dato = dato;
    }

    public NodoC(String dato) {
        this.dato = dato;
    }

    @Override
    public String toString() {
        return dato;
    }

 
    public NodoC() {
    }
}
