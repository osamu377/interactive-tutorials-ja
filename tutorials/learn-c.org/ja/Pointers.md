チュートリアル
-------------

ポインタも変数の一種であり、Cプログラミング言語において非常に重要な役割を果たします。ポインタは、以下のような様々な目的で使用されます。

* 文字列
* 動的メモリ割り当て
* 関数の引数を参照渡しする
* 複雑なデータ構造を構築する
* 関数へのポインタ
* 特殊なデータ構造（ツリー、トライなど）を構築する

その他多数。

### ポインタとは何ですか?

ポインタは本質的には、実際の値自体を保持するのではなく、値を指す **メモリ アドレス** を保持する単純な整数変数です。

コンピュータのメモリはデータを格納するための連続的な場所であり、ポインタはそのメモリの特定の部分を指し示します。プログラムでは、ポインタを広範囲のメモリ領域を指すように使用することができます。その範囲は、メモリ上の特定の一点からどれだけの量のデータを読み込むかによって決まります。

### ポインタとしての文字列

文字列については既に説明しましたが、ここではもう少し深く掘り下げて、C における文字列が実際に何であるかを理解します (C++ と混在する場合、他の文字列と区別するために C 文字列と呼ばれます)。

以下を見てください:

    char * name = "John";

この行は3つの処理を行います。

1. `name` というローカル（スタック）変数を割り当てます。これは1文字へのポインタです。
2. 文字列 "John" をプログラムメモリのどこかに出現させます（もちろん、コンパイルおよび実行後）。
3. `name` 引数を初期化し、`J` 文字の位置（メモリ内の文字列の残りの部分がそれに続きます）を指します。

`name` 変数に配列としてアクセスしようとすると、それはうまくいって、文字 `J` のASCIIコード値を返します。これは、`name` 変数が実際には文字列の先頭を正確に指しているためです。

メモリは連続的であることがわかっているため、メモリ内で次の文字に進むと、文字列の末尾 (ASCIIコード値が 0 の文字、`\0` と表記) に達するまで、文字列内の次の文字を受け取ると想定できます。

### Dereferencing

Dereferencing is the act of referring to where the pointer points, instead of the memory address. We are already using dereferencing in arrays - but we just didn't know it yet. The brackets operator - `[0]` for example, accesses the first item of the array. And since arrays are actually pointers, accessing the first item in the array is the same as dereferencing a pointer. Dereferencing a pointer is done using the asterisk operator `*`.

デリファレンスとは、メモリアドレスではなく、ポインタが指している場所を参照する動作です。配列では既にデリファレンスを使用していますが、今回はそのことを知らなかっただけです。例えば、括弧演算子 `[0]` は配列の最初の項目にアクセスします。配列は実際にはポインタなので、配列の最初の項目にアクセスすることはポインタをデリファレンスすることと同じです。ポインタをデリファレンスするには、アスタリスク演算子 `*` を使用します。

If we want to create an array that will point to a different variable in our stack, we can write the following code:

    /* define a local variable a */
    int a = 1;

    /* define a pointer variable, and point it to a using the & operator */
    int * pointer_to_a = &a;

    printf("The value a is %d\n", a);
    printf("The value of a is also %d\n", *pointer_to_a);

Notice that we used the `&` operator to point at the variable `a`, which we have just created.

We then referred to it using the dereferencing operator. We can also change the contents of the dereferenced variable:

    int a = 1;
    int * pointer_to_a = &a;

    /* let's change the variable a */
    a += 1;

    /* we just changed the variable again! */
    *pointer_to_a += 1;

    /* will print out 3 */
    printf("The value of a is now %d\n", a);

演習
----

Create a pointer to the local variable `n` called `pointer_to_n`, and use it to increase the value of `n` by one.

チュートリアル コード
-------------------

    #include <stdio.h>

    int main() {
      int n = 10;

      /* your code goes here */

      /* testing code */
      if (pointer_to_n != &n) return 1;
      if (*pointer_to_n != 11) return 1;

      printf("Done!\n");
      return 0;
    }

期待している出力
---------------

    Done!

解答
----

    #include <stdio.h>

    int main() {
      int n = 10;

      int * pointer_to_n = &n;

      *pointer_to_n += 1;

      /* testing code */
      if (pointer_to_n != &n) return 1;
      if (*pointer_to_n != 11) return 1;

      printf("Done!\n");
      return 0;
    }
