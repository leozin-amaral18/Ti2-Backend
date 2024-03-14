	package exercicio3;
	
	import static spark.Spark.*;

import java.util.List;
	
	
	public class Principal{
	    public static void main(String[] args) {	
	    	
	    	staticFiles.location("/public");    	
	   	        	
	       GarrafaDAO garrafaDAO = new GarrafaDAO(); 
	        
	
	                	post("/inserir_garrafa", (req, res) -> {
	             	        Garrafa garrafa = new Garrafa();
	                	    String cor = req.queryParams("cor");
	                	    double preco = Double.parseDouble(req.queryParams("preco"));
	                	    String marca = req.queryParams("marca");
	                	                            
	                        garrafa.setCor(cor);
	                        
	                        garrafa.setPreco(preco);
	                        
	                        garrafa.setMarca(marca);
	                        
	                        garrafaDAO.insert(garrafa);
	                	                    	                 	    
	                	    return null;
	                	});
	                	
	                	post("/atualizar_garrafa", (req, res) -> {
	             	        Garrafa garrafa = new Garrafa();
	             	        int id = Integer.parseInt(req.queryParams("id"));
	                	    String cor = req.queryParams("cor");
	                	    double preco = Double.parseDouble(req.queryParams("preco"));
	                	    String marca = req.queryParams("marca");
	                	                            
	                        garrafa.setCor(cor);
	                        
	                        garrafa.setPreco(preco);
	                        
	                        garrafa.setMarca(marca);
	                        
	                        garrafaDAO.update(garrafa, id);
	                	                    	                 	    
	                	    return null;
	                	});
	                	
	                	post("/remover_garrafa", (req, res) -> {
	             	        int id = Integer.parseInt(req.queryParams("id"));	                	                            
	                        
	                        garrafaDAO.delete(id);
	                	                    	                 	    
	                	    return null;
	                	});
	                	
	                	get("/listar_garrafas", (req, res) -> {
	                	    List<Garrafa> garrafas = garrafaDAO.list(Integer.parseInt(req.queryParams("id1")),Integer.parseInt(req.queryParams("id2"))); 

	                	    StringBuilder html = new StringBuilder();
	                	    html.append("<html>");
	                	    html.append("<head><title>Lista de Garrafas</title></head>");
	                	    html.append("<body>");
	                	    html.append("<h1>Garrafas:</h1>");
	                	    html.append("<ul>");
	                	    
	                	    for(Garrafa garrafa : garrafas) {
	                	        html.append("<li>Cor: ").append(garrafa.getCor())
	                	            .append(", Preço: ").append(garrafa.getPreco())
	                	            .append(", Marca: ").append(garrafa.getMarca()).append("</li>");
	                	    }
	                	    
	                	    html.append("</ul>");
	                	    html.append("</body>");
	                	    html.append("</html>");
	                	    
	                	    return html.toString();
	                	});
								
	
	
	    }
	}
