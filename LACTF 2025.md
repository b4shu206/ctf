## web/I spy...
> Token1: B218B51749AB9E4C669E4B33122C8AE3

Ta được gợi ý trong HTML Source truy cập vào thì có được
> Token2: 66E7AEBA46293C88D484CDAB0E479268 

Tiếp tục được gợi ý trong `javascript console` nên ta mở console (f12) lên và có được token thứ 3
> Token3: 5D1F98BCEE51588F6A7500C4DAEF8AD6

Hint tiếp theo là nó nằm trong `stylesheet` ta inspect thì thấy 1 file `style.css` mở lên thì đã thấy token4
> Token4: 29D3065EFED4A6F82F2116DA1784C265

Token 5 thì được gợi ý trong javascript code ta inspect thì thấy file `thingy.js` mở lên thì đã thấy token cần tìm
> Token5: 9D34859CA6FC9BB8A57DB4F444CDAE83

Được gợi ý là có 1 token trong header bật burpsuite thì có được token trong response
![image](https://hackmd.io/_uploads/HkiwfSe5Jl.png)
> Token6: BF1E1EAA5C8FDA6D9D0395B6EA075309

Token7 thì được gợi ý là nằm trong cookie, ta dùng devtool truy cập vào `Application` và lấy được token
![image](https://hackmd.io/_uploads/ByEkmBgqke.png)
> Token7: 647E67B4A8F4AA28FAB602151F1707F2

Tiếp tục ta có gợi ý là `A token where the robots are forbidden from visiting...` thì ở đây chỉ có file `robots.txt` thôi ta thử truy cập vào thì được đường dẫn `/a-magical-token.txt` tiếp tục truy cập vào thì đã có được token
> Token8: 3FB4C9545A6189DE5DE446D60F82B3AF

Hint tiếp theo là `A token where Google is told what pages to visit and index...` thì ngoài `robots.txt` thì ta còn file `sitemap.xml` truy cập vào thì đã có được token
> Token9: F1C20B637F1B78A1858A3E62B66C3799

Yêu cầu tiếp theo thì ta cần gửi request có method `DELETE` tới trang web thì ta có thể dùng curl để làm điều đó
`curl -X DELETE https://i-spy.chall.lac.tf`
![image](https://hackmd.io/_uploads/Hk5p7Sl9ke.png)
> Token10: 32BFBAEB91EFF980842D9FA19477A42E

Hint tiếp theo là `A token in a TXT record at i-spy.chall.lac.tf...` để đọc TXT record thì ta truy cập vào [trang web này](https://www.nslookup.io/txt-lookup/) và đã tìm được token
![image](https://hackmd.io/_uploads/BJc4Vrlc1g.png)
> Token11: 7227E8A26FC305B891065FE0A1D4B7D4

Submit và ta đã lấy được flag
![image](https://hackmd.io/_uploads/HytrVSlcJg.png)
> FLAG: lactf{1_sp0773d_z_t0k3ns_4v3rywh3r3}
