library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
entity cnt is
    Port ( clk : in  STD_LOGIC;
           clr : in  STD_LOGIC;
           count : out  STD_LOGIC_VECTOR (3 downto 0);
           t : inout  STD_LOGIC_VECTOR (3 downto 0);
           q : inout  STD_LOGIC_VECTOR (3 downto 0));
end cnt;

architecture Behavioral of cnt is

begin

t(0)<= (not q(0));
t(1)<= (((not q(1)) and q(0)) or (q(1) and (not q(0))));
t(2)<= ((q(2) and (not q(1))) or ((not q(0) and q(2))) or ( q(1) and q(0) and (not q(2))));
t(3)<= (((not q(3)) and q(2) and q(1) and q(0)) or (( not q(1)) and q(3)) or ( q(3) and (not q(2))) or ((not q(0)) and q(3)));

process (clk, clr) 
begin   
if (clr='1') then   
q <= "0000";  
        
elsif (Clk'event and Clk='1') then 
q <= t;
end if;     
end process; 
count <= q;
  
end Behavioral;
