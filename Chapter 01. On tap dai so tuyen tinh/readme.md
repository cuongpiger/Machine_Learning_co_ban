# 1. Lưu ý về kí hiệu
* Số vô hướng - chữ cái in nghiêng: $\mathit{x_1, N, y, k}$.
* Vector - chữ thường in đậm: $\mathbf{y, x_1}$.
  * **Vector hàng**: $\mathbf{x} = [x_1, x_2,...,x_n]$.
  * **Vector cột**: $\mathbf{x} = [x_1;x_2;...;x_n]$.
  * **LƯU Ý**: Nếu không nói gì thêm, các vector dc mặc định là **vector cột**.
* Ma trận - chữ hoa in đậm: $\mathbf{X, Y, W}$.
  * Ma trận được tạo thành từ các **vector cột** theo thứ tự **trái qua phải**: $\mathbf{X = [x_1, x_2,...,x_n]}$.
  * Ma trận được tạo thành từ các **vector hàng** theo thứ tự **trên xuống dưới**: $\mathbf{X = [x_1;x_2;...;x_n]}$.
  * Phần tử nằm ở dòng $i$ cột $j$ của ma trận kí hiệu là $x_{ij}$.
  * **LƯU Ý**: Cho ma trận $\mathbf{W}$, nếu không nói gì thêm thì $\mathbf{w_i}$ được hiểu là **vector cột** thứ $i$ của ma trận $\mathbf{W}$.

# 2. Chuyển vị và Hermitian
* Tên tiếng anh là **transpose**, kí hiệu là $T$.
* Cho $\mathbf{A} \in \mathbb{R}^{m \times n}$, ta nói $\mathbf{B} \in \mathbb{R}^{n \times m}$ là chuyển vị của $\mathbf{A}$ nếu:
  $$b_{ij} = a_{ji}, \forall1 \leq i \leq n, 1 \leq j \leq m$$
* Ví dụ:
  * Chuyển vị của vector $\mathbf{x}$ kí hiệu là $\mathbf{x}^T$.
    ![](images/01_00.png)
  * Chuyển vị của ma trận $\mathbf{A}$ kí hiệu là $\mathbf{A}^T$.
    ![](images/01_01.png)

* Ta có $\mathbf{A} \in \mathbb{R}^{m \times n}$ thì $\mathbf{A}^T \in \mathbb{R}^{n \times m}$. Nếu $\mathbf{A = A}^T$ thì $\mathbf{A}$ là **ma trận đối xứng** _(symmetric matrix)_.

<hr>

* Trong trường hợp vector hay ma trận có phần tử là **số phức**, thì việc lấy chuyển vị sẽ kèm theo **lấy liên hợp phức** của phần tử đó. Quá trình này được gọi ngắn gọn là **chuyển vị liên hợp** _(conjugate transpose)_, kí hiệu là $H$.
* Chuyển vị liên hợp của ma trận $\mathbf{A}$ là $\mathbf{A}^H$ _(còn được gọi là_ $\mathbf{A}$ Hermitian _)_.
* Cho $\mathbf{A} \in \mathbb{C}^{m \times n}$, ta nói $\mathbf{B} \in \mathbb{C}^{n \times m}$ là chuyển vị liên hợp của $\mathbf{A}$ nếu:
  $$b_{ij} = \overline{a_{ji}}, \forall 1 \leq i \leq n, 1 \leq j \leq m$$
  với $\overline{a}$ là liên hợp phức của $a$.

* Ví dụ:
  * Chuyển vị liên hợp của vector $\mathbf{x}$ kí hiệu là $\mathbf{x}^H$.
    ![](images/01_02.png)
  * Chuyển vị liên hợp của ma trận $\mathbf{A}$ kí hiệu là $\mathbf{A}^H$.
    ![](images/01_03.png)

* Nếu $\mathbf{A, x}$ lần lượt là các ma trận thực và vector thực thì:
  $$\mathbf{A}^H = \mathbf{A}^T, \mathbf{x}^H = \mathbf{x}^T$$

* Nếu chuyển vị liên hợp của một ma trận phức bằng với chính nó, $\mathbf{A}^H = \mathbf{A}$ thì nói gọi ma trận đó là **Hermittian**.

# 3. Phép nhân hai ma trận
* Cho hai ma trận $\mathbf{A} \in \mathbb{R}^{m \times n}, \mathbf{B} \in \mathbb{R}^{n \times p}$, thì tích của hai ma trận này kí hiệu là $\mathbf{C=AB} \in \mathbb{R}^{m \times p}$, khi đó phần tử tại dòng $i$ cột $j$ của ma trận kết quả được tính bởi:
  $$c_{ij} = \sum_{k=1}^{n}a_{ik} \times b_{kj}, \forall 1 \leq i \leq m, 1 \leq j \leq p$$

* Tính chất:
  * Không có tính chất giao hoán.
    $$\mathbf{AB} \neq \mathbf{BA}$$
  * Có tính chất kết hợp:
    $$\mathbf{ABC = (AB)C = A(BC)}$$
  * Có tính phân phối đối với phép cộng:
    $$\mathbf{A(B + C) = AB + AC}$$
  * Chuyển vị của một rích bằng tích các chuyển vị theo thứ tự **ngược lại**:
    $$\mathbf{(AB)^T}=\mathbf{B}^T \mathbf{A}^T, \mathbf{(AB)^H}=\mathbf{B}^H \mathbf{A}^H$$

<hr>

* Bằng cách coi vector là một trượng hợp đặc biệt của ma trận, ta có tích vô hướng của hai vector _(inner product)_ $\mathbf{x, y} \in \mathbb{R}^n$ được định nghĩa là:
  $$\mathbf{x}^T \mathbf{y} = \mathbf{y}^T \mathbf{x} = \sum_{i=1}^{n} x_i \times y_i$$

* **LƯU Ý**: 
  $$\mathbf{x}^H \mathbf{y} = \mathbf{y}^H \mathbf{x} = (\mathbf{y}^H \mathbf{x})^H$$
  khi và chỉ khi chúng là các số thực.

  $$\mathbf{x}^H\mathbf{x} \geq 0, \forall \mathbf{x} \in \mathbb{C}^n$$

* Nếu tích vô hướng của **hai vector khác không** bằng không, thì hai vector đó **vuông góc với nhau**.

<hr>

* Phép nhân của một ma trận $\mathbf{A} \in \mathbb{R}^{m \times n}$ với một vector $\mathbf{x} \in \mathbb{R}^n$ là một vector $\mathbf{b} \in \mathbb{R}^m$:
  $$\mathbf{Ax = b}, \text{với } b_i = \mathbf{A}_{:,i} \mathbf{x}$$
  với $\mathbf{A}_{:,i}$ là vector hàng thứ $i$ của ma trận $\mathbf{A}$.

* Ngoài ra còn có một phép nhân khác gọi là **Hadamard** _(còn được gọi là Element-wise)_ hay được sử dụng trong Machine Learning. Tích Hadamard của hai ma trận có **cùng kích thước** $\mathbf{A, B} \in \mathbb{R}^{m \times n}$ được định nghĩa là:
  $$\mathbf{C = A \odot B} \in \mathbb{R}^{m \times n}, \text{với } c_{ij} = a_{ij} \times b_{ij}$$

# 4. Ma trận đơn vị và ma trận nghịch đảo
## 4.1. Ma trận đơn vị
* **Đường chéo chính** của một ma trận là tập hợp các phần tử có chỉ số hàng và chỉ số cột như nhau. Các định nghĩa này cũng áp dụng trên các ma trận không vuông.

* Nếu ma trận $\mathbf{A} \in \mathbb{R}^{m \times n}$ thì đường chéo chính của $\mathbf{A}$ gồm các phần tử:
  $$\{a_{11}, a_{22},...,a_{pp} \}, \text{với } p = min\{m, n\}$$

* Một ma trận đơn vị bậc $n$ là một ma trận trận thuộc $\mathbb{R}^{n \times n}$ với các phần tử nằm trên đường chéo chính bằng $1$, các phần tử còn lại bằng $0$ và ma trận này được kí hiệu là $\mathbf{I}$ _(identity matrix)_.

* Ma trận đơn vị bậc $n$ được kí hiệu là $\mathbf{I}_n$. Ví dụ:
  ![](images/01_04.png)

* Giả sử có $\mathbf{A} \in \mathbb{R}^{m \times n}, \mathbf{B} \in \mathbb{R}^{n \times m}$ và $\mathbf{I}_n$ thì:
  $$\mathbf{AI = A, IB = B}$$

* Với mọi vector $\mathbf{x} \in \mathbb{R}^n$ thì:
  $$\mathbf{I}_n \mathbf{x = x}$$

## 4.2. Ma trận nghịch đảo
* Một **ma trận vuông** $\mathbf{A} \in \mathbb{R}^{n \times n}$, nếu **tồn tại một ma trận vuông** $\mathbf{B} \in \mathbb{R}^{n \times n}$ sao cho:
  $$\mathbf{AB = I}$$
  * Thì $\mathbf{B}$ được gọi là **ma trận nghịch đảo** _(inverse matrix)_ của $\mathbf{A}$ và lúc này $\mathbf{A}$ được gọi là **khả nghịch** _(invertible, nonsingular, nondegenerate)_.
  * Nếu không tồn tại ma trận $\mathbf{B}$ thỏa điều kiện trên thì ta nói ma trận $\mathbf{A}$ **không khả nghịch** _(singular, degenerate)_.

* Nếu $\mathbf{A}$ khả nghịch thì ma trận nghịch đảo của $\mathbf{A}$ kí hiệu là $\mathbf{A^{-1}}$.
* Ma trận nghịch đảo được sử dụng để giải hệ phương trình tuyến tính. Giả sử $\mathbf{A} \in \mathbb{R}^{n \times n}$ là một ma trận khả nghịch và một vector $\mathbf{b} \in \mathbb{R}^n$ bất kì. Khi đó, phương trình:
  $$\mathbf{Ax = b}$$
  có nghiệm duy nhất $\mathbf{x = A^{-1}b }$.

* Giả sử hai ma trận $\mathbf{A, B}$ là hai ma trận khả nghịch thì **tích của chúng cũng khả nghịch** và:
  $$\mathbf{(AB)^{-1} = B^{-1}A^{-1}}$$

# 5. Một vài ma trận đặc biệt khác
## 5.1. Ma trận đường chéo
* **Ma trận đường chéo** _(diagonal matrix)_ là ma trận chỉ có các thành phần trên đường chéo chính **khác không**. Định nghĩa này cũng áp dụng cho các ma trận ko vuông.
* **Ma trận không** là ma trận có tất cả các phần tử trong ma trận bằng không.
* Ma trận không và ma trận đơn vi cũng được gọi là các ma trận đường chéo.
* Một vài ví dụ về ma trận đường chéo:
  ![](images/01_05.png)

* Với các **ma trận đường chéo vuông**, thay vì viết cả ma trận, ta có thể chỉ liệt kê các thành phần nằm trên đường chéo chính. Ví dụ một ma trận đường chéo vuông $\mathbf{A} \in \mathbb{R}^{m \times m}$ có thể dc kí hiệu là:
  $$diag(a_{11}, a_{22},...,a_{nn})$$
  với $a_{ii}$ là phần tử nằm ở dòng $i$ cột $i$ của ma trận $\mathbf{A}$.

* Tích, tổng của hai ma trận đường chéo vuông **cùng bậc** cũng là một ma trận đường chéo vuông.
* Một ma trận đường chéo vuông khả nghịch nếu mọi phần từ nằm trên đường chéo chính khác không.
* Nghịch đảo của một ma trận đường chéo vuông khả nghịch cũng là một ma trận đường chéo, cụ thể:
  $$(diag(a_1, a_2,...,a_n))^{-1} = diag(a_1^{-1}, a_2^{-1},...,a_n^{-1})$$

## 5.2. Ma trận tam giác
* Một ma trận vuông dc gọi là **ma trận tam giác trên** _(upper triangular matrix)_ nếu tất cả các thành phần nằm dưới đường chéo chính bằng không.
* Một ma trận vuông dc gọi là **ma trận tam giác dưới** _(lower triangular matrix)_ nếu tất cả các thành phần nằm trên đường chéo chính bằng không.
* Xét hệ:
  ![](images/01_06.png)
  * Hệ này có thể dc viết gọn dưới dạng $\mathbf{Ax = b}$ với $\mathbf{A}$ là ma trận tam giác trên.
  * Hệ phương trình này có thể được giải mà không cần tìm ma trận nghịch đảo $\mathbf{A^{-1}}$.
  * Nếu ma trận $\mathbf{A}$ là ma trận tam giác trên thì có thể áp dụng phương pháp **back substituation**.
  * Nếu ma trận $\mathbf{A}$ là ma trận tam giác dưới thì có thể áp dụng phương pháp **forward substituation**.

# 6. Định thức
## 6.1. Định nghĩa
* Định thức của một ma trận $\mathbf{A}$ được kí hiệu là $det(\mathbf{A})$.
* Với $n=1$, $det(\mathbf{A})$ chính là phần tử duy nhất của ma trận đó.
* Với ma trận vuông bậc $n > 1$ thì:
  ![](images/01_07.png)
  * Trong đó $i$ là một giá trị bất kì sao cho $1 \leq i \leq n$ và $\mathbf{A}_{ij}$ là **phần bù đại số** của $\mathbf{A}$ bằng cách xóa đi dòng $i$ và cột $j$ của ma trận $\mathbf{A}$ ban đầu.

## 6.2. Tính chất
* $det(\mathbf{A}) = det(\mathbf{A}^T)$
* Định thức của một ma trận đường chéo vuông bằng tích các phần tử nằm trên đường chéo chính.
* Định thức của ma trận đơn vị bằng $1$.
* Định thức của một tích bằng tích các định thức:
  $$det(\mathbf{AB}) = det(\mathbf{A})det(\mathbf{B})$$
  với $\mathbf{A, B}$ là hai ma trận vuông cùng chiều.

* Nếu ma trận có một vector hàng hoặc vector cột là một vector không thì định thức của ma trận này bằng $0$.
* Một ma trận khả nghịch khi và chỉ khi định thức của nó khác $0$.
* Nếu một ma trận khả nghịch, định thức của ma trận nghịch đảo bằng nghịch đảo định thức của ma trận ban đầu.
  ![](images/01_08.png)