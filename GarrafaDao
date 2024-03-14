package exercicio3;

import java.sql.*;
import java.util.ArrayList;
import java.util.List;

public class GarrafaDAO extends DAO{
	
	public GarrafaDAO() {
		super();
		conectar();
	}

	public void finalize() {
		close();
	}
	
	public int fetchGarrafaId(Garrafa garrafa) {
	    try {
	        Statement st = conexao.createStatement();

	        String sql = "SELECT id FROM garrafa WHERE cor = '" + garrafa.getCor() + "' AND preco = " + garrafa.getPreco() + " AND marca = '" + garrafa.getMarca() + "' LIMIT 1";

	        ResultSet rs = st.executeQuery(sql);

	        if (rs.next()) {
	            return rs.getInt("id");
	        }
	        st.close();
	    } catch (SQLException e) {
	        e.printStackTrace();
	    }

	    return -1;  
	}

	
	
	public boolean insert(Garrafa garrafa) {
		boolean status = false;
		try {  
			Statement st = conexao.createStatement();
			String sql = "INSERT INTO \"garrafa\" (\"cor\", \"preco\", \"marca\") "
			           + "VALUES ('" + garrafa.getCor() + "', " + garrafa.getPreco() 
			           + ", '" + garrafa.getMarca() + "');";
			System.out.println(sql);

			st.executeUpdate(sql);
			st.close();
			status = true;
			
			System.out.println(garrafa.toString());
			
		} catch (SQLException u) {  
			throw new RuntimeException(u);
		}
		return status;
	}
	
	public boolean update(Garrafa garrafa, int id) {
	    boolean status = false;
	    try {  
	        Statement st = conexao.createStatement();
	        String sql = "UPDATE garrafa SET cor = '" + garrafa.getCor() + "', preco = "  
	                   + garrafa.getPreco() + ", marca = '" + garrafa.getMarca() + "'"
	                   + " WHERE id = " + id;
	        System.out.println(sql);
	        st.executeUpdate(sql);
	        st.close();
	        status = true;
	        
	        
	    } catch (SQLException u) {  
	        throw new RuntimeException(u);
	    }
	    return status;
	}
	
	public boolean delete(int id) {
		boolean status = false;
		try {  
			Statement st = conexao.createStatement();
			String sql = "DELETE FROM garrafa WHERE id = " + id;
			System.out.println(sql);
			st.executeUpdate(sql);
			st.close();
			status = true;
		} catch (SQLException u) {  
			throw new RuntimeException(u);
		}
		return status;
	}
	public List<Garrafa> list(int id1, int id2) {
	    List<Garrafa> garrafas = new ArrayList<Garrafa>();
	    
	    try {  
	        Statement st = conexao.createStatement();
	        
	        String sql = "SELECT * FROM garrafa WHERE id BETWEEN " + id1 + " AND " + id2;
	        System.out.println(sql);
	        
	        ResultSet rs = st.executeQuery(sql);
	        
	        while(rs.next()) {
	            Garrafa garrafa = new Garrafa();
	            garrafa.setCor(rs.getString("cor"));
	            garrafa.setPreco(rs.getInt("preco"));
	            garrafa.setMarca(rs.getString("marca"));
	            garrafas.add(garrafa);
	        }
	        
	        for (Garrafa g : garrafas) {
	        	System.out.println(g.toString());
	        }
	        
	        rs.close();
	        st.close();
	        
	    } catch (SQLException u) {  
	        throw new RuntimeException(u);
	    }
	    
	    return garrafas;
	}


	

}
