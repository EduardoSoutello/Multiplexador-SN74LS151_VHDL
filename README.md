LIBRARY IEEE;
USE IEEE.STD_LOGIC_1164.ALL;

ENTITY multiplex IS
	 PORT ( 
			enable: 							IN STD_LOGIC;
			x0, x1, x2 ,x3, x4, x5, x6, x7: 				IN STD_LOGIC;
			s1, s2, s3:							IN STD_LOGIC;
			otmux, otmuxn: 		  			OUT STD_LOGIC
				
	);
END multiplex;

ARCHITECTURE SN74LS151 OF multiplex IS
	BEGIN
	
		otmux <= x0 WHEN s1 = '0' AND s2 = '0' AND s3 = '0' AND enable = '1' ELSE 
					x1 WHEN s1 = '0' AND s2 = '0' AND s3 = '1' AND enable = '1' ELSE 
					x2 WHEN s1 = '0' AND s2 = '1' AND s3 = '0'  AND enable = '1'ELSE 
					x3 WHEN s1 = '0' AND s2 = '1' AND s3 = '1'  AND enable = '1'ELSE 
					x4 WHEN s1 = '1' AND s2 = '0' AND s3 = '0'  AND enable = '1'ELSE 
					x5 WHEN s1 = '1' AND s2 = '0' AND s3 = '1'  AND enable = '1'ELSE 
					x6 WHEN s1 = '1' AND s2 = '1' AND s3 = '0'  AND enable = '1'ELSE
					x7;
					
		otmuxn <= NOT x0 WHEN s1 = '0' AND s2 = '0' AND s3 = '0'  AND enable = '1'ELSE 
					NOT x1 WHEN s1 = '0' AND s2 = '0' AND s3 = '1'   AND enable = '1'ELSE 
					NOT x2 WHEN s1 = '0' AND s2 = '1' AND s3 = '0'   AND enable = '1'ELSE 
					NOT x3 WHEN s1 = '0' AND s2 = '1' AND s3 = '1'   AND enable = '1'ELSE 
					NOT x4 WHEN s1 = '1' AND s2 = '0' AND s3 = '0'   AND enable = '1'ELSE 
					NOT x5 WHEN s1 = '1' AND s2 = '0' AND s3 = '1'   AND enable = '1'ELSE 
					NOT x6 WHEN s1 = '1' AND s2 = '1' AND s3 = '0'   AND enable = '1'ELSE
					NOT x7;				
END ARCHITECTURE;
