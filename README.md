# Tarea2-Colas
public class Main {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // TODO code application logic here
        
        Cola laCola = new Cola();
        Cola aux = new Cola();
        Cola pref = new Cola();
        boolean salir = false;
        while(!salir){
            int opt = Integer.parseInt(JOptionPane.showInputDialog("Menu: \n 1. cliente regular \n 2.Cliente preferencial \n 3. Ver Fila \n 4. Salir"));
            switch (opt) {
                case 1:
                    String cedula = JOptionPane.showInputDialog("Digite el numero de cedula");
                    laCola.encola(cedula);
                    break;
                case 2:
                    String cliPref = JOptionPane.showInputDialog("Digite el numero de cedula");
                    pref.encola("P-"+cliPref);
                    boolean vaciarCola = true;
                    while(vaciarCola){
                        String dato = laCola.atiende();
                        if (dato == null) {
                            vaciarCola = false;
                        }else{
                            aux.encola(dato);
                        }
                    }
                    boolean colaPref =  true;
                    while(colaPref){
                        String CliPref = pref.atiende();
                        
                        if(CliPref == null){
                            colaPref = false;
                        }else{
                            laCola.encola(CliPref);
                        }
                    }
                    boolean reEncolar =  true;
                    while(reEncolar){
                        String Cliente = aux.atiende();
                        
                        if(Cliente == null){
                            reEncolar = false;
                        }else {
                            laCola.encola(Cliente);
                        }
                    }
                    break;
                case 3:
                    JOptionPane.showMessageDialog(null, laCola);
                    break;
                case 4:
                    salir = true;
                    break;
                default:
                    JOptionPane.showMessageDialog(null, "Digite una opcion valida");
            }
        }

    }
    
    public void Preferencial(){
    
    }
    }
