module bcd_adder(a,b,cin,s,cout);
input [3:0]a,b;
input cin;
output reg [3:0]s;
output reg cout;
reg [4:0]temp_sum;
always @(a or b or cin)
begin
if (a>10||b>10)
begin 
$display("Invalid input");
elif (a<10 && b<10)
temp_sum=a+b+cin;
if(temp_sum>9)
begin
temp_sum=temp_sum+6;
s=temp_sum[3:0];
cout=1;
end
else 
begin
s=temp_sum[3:0];
cout=0;
end
end
end
endmodule