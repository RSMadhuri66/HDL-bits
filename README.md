Question 1 - Wire 

Answer - assign out = in; 

Question 2 - Wire4

Answer - module top_module( 
    input a,b,c,
    output w,x,y,z );
    
    assign w = a; 
    assign x = b; 
    assign y = b; 
    assign z = c; 

endmodule

Question 3 - Notgate

Answer - module top_module( input in, output out );

    assign out = ~ in; 
endmodule

Question 4 - Andgate 

Answer - module top_module( 
    input a, 
    input b, 
    output out );
    
    assign out = a&b; 

endmodule


