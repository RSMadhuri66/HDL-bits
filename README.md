Question 1 - Wire 

Answer - assign out = in; 

Question 2 - Wire4

Answer -  
```
module top_module( 
    input a,b,c,
    output w,x,y,z );
    
    assign w = a; 
    assign x = b; 
    assign y = b; 
    assign z = c; 

endmodule
```

Question 3 - Notgate

Answer - 
```
module top_module( input in, output out );

    assign out = ~ in; 
endmodule
```

Question 4 - Andgate 

Answer - 
```
module top_module( 
    input a, 
    input b, 
    output out );
    
    assign out = a&b; 

endmodule
```

Question 5 - Norgate

Answer - 
```
module top_module( 
    input a, 
    input b, 
    output out );
    
    assign out = ~ (a | b ) ; 

endmodule
```

Question 6 - Xnorgate

Answer - 
```
module top_module( 
    input a, 
    input b, 
    output out );
    
    assign out = ~ ( a ^ b ) ;

endmodule

```

Question 7 - Wire decl 

Answer - 

```
`default_nettype none
module top_module(
    input a,
    input b,
    input c,
    input d,
    output out,
    output out_n   ); 
    
    wire one ; 
    wire two; 
    
    assign one = a & b ; 
    assign two = c & d ; 
    
    assign out = one || two ; 
    assign out_n = ~ out ; 

endmodule

```

Question 8 - 7458 

Answer - 

```
module top_module ( 
    input p1a, p1b, p1c, p1d, p1e, p1f,
    output p1y,
    input p2a, p2b, p2c, p2d,
    output p2y );

    wire one, two, three, four; 
    
     assign one = p2a & p2b; 
     assign two = p2c & p2d; 
    
    assign three = p1b & p1c & p1a ; 
    assign four = p1f &  p1e & p1d  ; 
    
     assign p2y = one | two ; 
    
     assign p1y = three | four ; 
    

endmodule

```

Question 9 - Vector0 

Answer - 

```
module top_module ( 
    input wire [2:0] vec,
    output wire [2:0] outv,
    output wire o2,
    output wire o1,
    output wire o0  ); // Module body starts after module declaration
    
    assign outv = vec; 
    
    assign o2 = outv[2]; 
    assign o1 = outv[1]; 
    assign o0 = outv[0]; 

endmodule

```

Question 10 - Vector1

Answer - 

```
`default_nettype none     // Disable implicit nets. Reduces some types of bugs.
module top_module( 
    input wire [15:0] in,
    output wire [7:0] out_hi,
    output wire [7:0] out_lo );
    
    assign out_hi [7:0] = in [15:8] ; 
    assign out_lo [7:0] = in[7:0]; 

endmodule

```

Question 11 - Vector2 

Answer - 

```
module top_module( 
    input [31:0] in,
    output [31:0] out );//

    assign out[31:24] = in[7:0];
    assign out[23 :16] = in[15:8];
    assign out[15:8] = in[23:16];
    assign out[7:0] = in[31:24];

endmodule

```

Question 12 - Vectorgates

Answer - 

```
module top_module( 
    input [2:0] a,
    input [2:0] b,
    output [2:0] out_or_bitwise,
    output out_or_logical,
    output [5:0] out_not
);
    
    assign out_or_bitwise = a|b ; 
    assign out_or_logical = a||b; 
    
    assign  out_not [2:0] = ~a; 
    assign out_not  [5:3]  = ~b; 

endmodule

```

Question 13 - Gates4 

Answer - 

```
module top_module( 
    input [3:0] in,
    output out_and,
    output out_or,
    output out_xor
);
    wire a, b, c, d; 
     
    assign a = in[0];
    assign b = in[1];
    assign c = in[2];
    assign d = in[3]; 
    
    assign out_and = a & b & c & d; 
    assign out_or = a || b || c || d ; 
    assign out_xor = a ^ b ^ c ^ d; 

endmodule

```

Question 14 - Vector3 

Answer - 

```
module top_module (
    input [4:0] a, b, c, d, e, f,
    output [7:0] w, x, y, z 
);

    wire [31:0] conc; 
    
    assign conc = {a, b, c, d, e, f, 2'b11} ; 
    assign w =  conc [31:24]; 
    assign x = conc [23:16] ; 
    assign y =  conc [15:8]; 
    assign z = conc [7:0] ; 
    

endmodule

```

Question 15 - Vectorr 

Answer - 

```
module top_module( 
    input [7:0] in,
    output [7:0] out
);
    
    assign out [7] = in [0]; 
    assign out [6] = in [1]; 
    assign out [5] = in [2]; 
    assign out [4] = in [3]; 
    assign out [3] = in [4]; 
    assign out [2] = in [5]; 
    assign out [1] = in [6]; 
    assign out [0] = in [7]; 
    
endmodule

```

Question 16 - Vector4 

Answer - 

```
module top_module (
    input [7:0] in,
    output [31:0] out );//

    assign out = { {24{in[7]}} , in } ;

endmodule

```

Question 17 - Vector5

Answer - 

```

module top_module (
    input a, b, c, d, e,
    output [24:0] out );

    // The output is XNOR of two vectors created by 
    // concatenating and replicating the five inputs.
    // assign out = ~{ ... } ^ { ... };
    
    assign out = ~ { {5{a}}, {5{b}}, {5{c}}, {5{d}}, {5{e}} } ^ {5{a,b,c,d,e}} ; 
    
    

endmodule

```


