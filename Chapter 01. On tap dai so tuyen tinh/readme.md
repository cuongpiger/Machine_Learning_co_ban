# 1. Lưu ý về kí hiệu
* Số vô hướng - chữ cái in nghiêng: $\mathit{x_1, N, y, k}$.
* Vector - chữ thường in đậm: $\mathbf{y, x_1}$.
  * **Vector hàng**: $\mathbf{x} = [x_1, x_2,...,x_n]$.
  * **Vector cột**: $\mathbf{x} = [x_1;x_2;...;x_n]$.
  * **LƯU Ý**: Nếu không nói gì thêm, các vector dc mặc định là **vector cột**.
* Ma trận - chữ hoa in đậm: $\mathbf{X, Y, W}$.
  * Ma trận được tạo thành từ các **vector cột** theo thứ tự **trái qua phải**: $\mathbf{X = [x_1, x_2,...,x_n]}$.
  * Ma trận đuôc tạo thành từ các **vector hàng** theo thứ tự **trên xuống dưới**: $\mathbf{X = [x_1;x_2;...;x_n]}$.
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
