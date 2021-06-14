#  1. Lưu ý về kí hiệu
  
* Số vô hướng - chữ cái in nghiêng: <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathit{x_1,%20N,%20y,%20k}"/>.
* Vector - chữ thường in đậm: <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{y,%20x_1}"/>.
  * **Vector hàng**: <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{x}%20=%20[x_1,%20x_2,...,x_n]"/>.
  * **Vector cột**: <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{x}%20=%20[x_1;x_2;...;x_n]"/>.
  * **LƯU Ý**: Nếu không nói gì thêm, các vector dc mặc định là **vector cột**.
* Ma trận - chữ hoa in đậm: <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{X,%20Y,%20W}"/>.
  * Ma trận được tạo thành từ các **vector cột** theo thứ tự **trái qua phải**: <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{X%20=%20[x_1,%20x_2,...,x_n]}"/>.
  * Ma trận đuôc tạo thành từ các **vector hàng** theo thứ tự **trên xuống dưới**: <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{X%20=%20[x_1;x_2;...;x_n]}"/>.
  * Phần tử nằm ở dòng <img src="https://latex.codecogs.com/gif.latex?i"/> cột <img src="https://latex.codecogs.com/gif.latex?j"/> của ma trận kí hiệu là <img src="https://latex.codecogs.com/gif.latex?x_{ij}"/>.
  * **LƯU Ý**: Cho ma trận <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{W}"/>, nếu không nói gì thêm thì <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{w_i}"/> được hiểu là **vector cột** thứ <img src="https://latex.codecogs.com/gif.latex?i"/> của ma trận <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{W}"/>.
  
#  2. Chuyển vị và Hermitian
  
* Tên tiếng anh là **transpose**, kí hiệu là <img src="https://latex.codecogs.com/gif.latex?T"/>.
* Cho <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A}%20&#x5C;in%20&#x5C;mathbb{R}^{m%20&#x5C;times%20n}"/>, ta nói <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{B}%20&#x5C;in%20&#x5C;mathbb{R}^{n%20&#x5C;times%20m}"/> là chuyển vị của <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A}"/> nếu:
  <p align="center"><img src="https://latex.codecogs.com/gif.latex?b_{ij}%20=%20a_{ji},%20&#x5C;forall1%20&#x5C;leq%20i%20&#x5C;leq%20n,%201%20&#x5C;leq%20j%20&#x5C;leq%20m"/></p>  
  
* Ví dụ:
  * Chuyển vị của vector <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{x}"/> kí hiệu là <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{x}^T"/>.
    ![](images/01_00.png )
  * Chuyển vị của ma trận <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A}"/> kí hiệu là <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A}^T"/>.
    ![](images/01_01.png )
  
* Ta có <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A}%20&#x5C;in%20&#x5C;mathbb{R}^{m%20&#x5C;times%20n}"/> thì <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A}^T%20&#x5C;in%20&#x5C;mathbb{R}^{n%20&#x5C;times%20m}"/>. Nếu <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A%20=%20A}^T"/> thì <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A}"/> là **ma trận đối xứng** _(symmetric matrix)_.
  
<hr>
  
* Trong trường hợp vector hay ma trận có phần tử là **số phức**, thì việc lấy chuyển vị sẽ kèm theo **lấy liên hợp phức** của phần tử đó. Quá trình này được gọi ngắn gọn là **chuyển vị liên hợp** _(conjugate transpose)_, kí hiệu là <img src="https://latex.codecogs.com/gif.latex?H"/>.
* Chuyển vị liên hợp của ma trận <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A}"/> là <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A}^H"/> _(còn được gọi là_ <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A}"/> Hermitian _)_.
* Cho <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A}%20&#x5C;in%20&#x5C;mathbb{C}^{m%20&#x5C;times%20n}"/>, ta nói <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{B}%20&#x5C;in%20&#x5C;mathbb{C}^{n%20&#x5C;times%20m}"/> là chuyển vị liên hợp của <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A}"/> nếu:
  <p align="center"><img src="https://latex.codecogs.com/gif.latex?b_{ij}%20=%20&#x5C;overline{a_{ji}},%20&#x5C;forall%201%20&#x5C;leq%20i%20&#x5C;leq%20n,%201%20&#x5C;leq%20j%20&#x5C;leq%20m"/></p>  
  
  với <img src="https://latex.codecogs.com/gif.latex?&#x5C;overline{a}"/> là liên hợp phức của <img src="https://latex.codecogs.com/gif.latex?a"/>.
  
* Ví dụ:
  * Chuyển vị liên hợp của vector <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{x}"/> kí hiệu là <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{x}^H"/>.
    ![](images/01_02.png )
  * Chuyển vị liên hợp của ma trận <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A}"/> kí hiệu là <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A}^H"/>.
    ![](images/01_03.png )
  
* Nếu <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A,%20x}"/> lần lượt là các ma trận thực và vector thực thì:
  <p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A}^H%20=%20&#x5C;mathbf{A}^T,%20&#x5C;mathbf{x}^H%20=%20&#x5C;mathbf{x}^T"/></p>  
  
  
* Nếu chuyển vị liên hợp của một ma trận phức bằng với chính nó, <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A}^H%20=%20&#x5C;mathbf{A}"/> thì nói gọi ma trận đó là **Hermittian**.
  
#  3. Phép nhân hai ma trận
  
* Cho hai ma trận <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A}%20&#x5C;in%20&#x5C;mathbb{R}^{m%20&#x5C;times%20n},%20&#x5C;mathbf{B}%20&#x5C;in%20&#x5C;mathbb{R}^{n%20&#x5C;times%20p}"/>, thì tích của hai ma trận này kí hiệu là <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{C=AB}%20&#x5C;in%20&#x5C;mathbb{R}^{m%20&#x5C;times%20p}"/>, khi đó phần tử tại dòng <img src="https://latex.codecogs.com/gif.latex?i"/> cột <img src="https://latex.codecogs.com/gif.latex?j"/> của ma trận kết quả được tính bởi:
  <p align="center"><img src="https://latex.codecogs.com/gif.latex?c_{ij}%20=%20&#x5C;sum_{k=1}^{n}a_{ik}%20&#x5C;times%20b_{kj},%20&#x5C;forall%201%20&#x5C;leq%20i%20&#x5C;leq%20m,%201%20&#x5C;leq%20j%20&#x5C;leq%20p"/></p>  
  
  
* Tính chất:
  * Không có tính chất giao hoán.
    <p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{AB}%20&#x5C;neq%20&#x5C;mathbf{BA}"/></p>  
  
  * Có tính chất kết hợp:
    <p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{ABC%20=%20(AB)C%20=%20A(BC)}"/></p>  
  
  * Có tính phân phối đối với phép cộng:
    <p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A(B%20+%20C)%20=%20AB%20+%20AC}"/></p>  
  
  * Chuyển vị của một rích bằng tích các chuyển vị theo thứ tự **ngược lại**:
    <p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{(AB)^T}=&#x5C;mathbf{B}^T%20&#x5C;mathbf{A}^T,%20&#x5C;mathbf{(AB)^H}=&#x5C;mathbf{B}^H%20&#x5C;mathbf{A}^H"/></p>  
  
  
<hr>
  
* Bằng cách coi vector là một trượng hợp đặc biệt của ma trận, ta có tích vô hướng của hai vector _(inner product)_ <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{x,%20y}%20&#x5C;in%20&#x5C;mathbb{R}^n"/> được định nghĩa là:
  <p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{x}^T%20&#x5C;mathbf{y}%20=%20&#x5C;mathbf{y}^T%20&#x5C;mathbf{x}%20=%20&#x5C;sum_{i=1}^{n}%20x_i%20&#x5C;times%20y_i"/></p>  
  
  
* **LƯU Ý**: 
  <p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{x}^H%20&#x5C;mathbf{y}%20=%20&#x5C;mathbf{y}^H%20&#x5C;mathbf{x}%20=%20(&#x5C;mathbf{y}^H%20&#x5C;mathbf{x})^H"/></p>  
  
  khi và chỉ khi chúng là các số thực.
  
  <p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{x}^H&#x5C;mathbf{x}%20&#x5C;geq%200,%20&#x5C;forall%20&#x5C;mathbf{x}%20&#x5C;in%20&#x5C;mathbb{C}^n"/></p>  
  
  
* Nếu tích vô hướng của **hai vector khác không** bằng không, thì hai vector đó **vuông góc với nhau**.
  
<hr>
  
* Phép nhân của một ma trận <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A}%20&#x5C;in%20&#x5C;mathbb{R}^{m%20&#x5C;times%20n}"/> với một vector <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{x}%20&#x5C;in%20&#x5C;mathbb{R}^n"/> là một vector <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{b}%20&#x5C;in%20&#x5C;mathbb{R}^m"/>:
  <p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{Ax%20=%20b},%20&#x5C;text{với%20}%20b_i%20=%20&#x5C;mathbf{A}_{:,i}%20&#x5C;mathbf{x}"/></p>  
  
  với <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A}_{:,i}"/> là vector hàng thứ <img src="https://latex.codecogs.com/gif.latex?i"/> của ma trận <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A}"/>.
  
* Ngoài ra còn có một phép nhân khác gọi là **Hadamard** _(còn được gọi là Element-wise)_ hay được sử dụng trong Machine Learning. Tích Hadamard của hai ma trận có **cùng kích thước** <img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{A,%20B}%20&#x5C;in%20&#x5C;mathbb{R}^{m%20&#x5C;times%20n}"/> được định nghĩa là:
  <p align="center"><img src="https://latex.codecogs.com/gif.latex?&#x5C;mathbf{C%20=%20A%20&#x5C;odot%20B}%20&#x5C;in%20&#x5C;mathbb{R}^{m%20&#x5C;times%20n},%20&#x5C;text{với%20}%20c_{ij}%20=%20a_{ij}%20&#x5C;times%20b_{ij}"/></p>  
  
  