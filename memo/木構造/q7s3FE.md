ご提示いただいた公開問題（令和5年度〜令和7年度）の記述形式に基づき、「木構造（ツリー構造）」をテーマにした擬似言語の演習問題を5問作成しました。



資料のルールである「要素番号は1から始まる」、メンバアクセスに「.」演算子を用いる、再帰呼び出しの構造 などを反映しています。



---



### 問1：二分探索木の走査（通りがけ順）

次の関数 inOrder は、二分探索木の各ノードを「通りがけ順（左の子→自分→右の子）」で巡回し、値を昇順に出力する再帰的なプログラムである。空欄に入る適切な記述を選べ。



〔プログラム〕

〇inOrder(Node: node)

    if (node が 未定義 でない)

        inOrder(node.left)

        node.value を出力する

        【　空欄　】

    endif



【解答群】

ア　inOrder(node.left)

イ　inOrder(node.right)

ウ　node.value ← 未定義の値

エ　return node.value



---



### 問2：二分探索木における値の探索

次の関数 searchBST は、二分探索木の根 root と探索したい値 target を受け取り、値が存在すれば true、存在しなければ false を返す。空欄に入る条件式として正しいものを選べ。



〔プログラム〕

〇論理型: searchBST(Node: root, 整数型: target)

    Node: current ← root

    while (current が 未定義 でない)

        if (current.value ＝ target)

            return true

        elseif (【　空欄　】)

            current ← current.left

        else

            current ← current.right

        endif

    endwhile

    return false



【解答群】

ア　target ＜ current.value

イ　target ＞ current.value

ウ　current.left が 未定義 である

エ　target ＝ 0



---



### 問3：二分木の高さの計算

次の関数 getHeight は、二分木の根を受け取り、その木の高さ（根から最も遠い葉までのノード数）を返す再帰関数である。空欄に入る適切な式を選べ。

ここで、関数 max(a, b) は a と b のうち大きい方の値を返すものとする。


〔プログラム〕

〇整数型: getHeight(Node: node)

    if (node が 未定義 である)

        return 0

    endif

    return 【　空欄　】



【解答群】

ア　getHeight(node.left) ＋ getHeight(node.right)

イ　max(getHeight(node.left), getHeight(node.right)) ＋ 1

ウ　getHeight(node.left) ＋ 1

エ　max(node.left, node.right)



---



### 問4：配列で表現された二分木の親ノード

完全二分木を要素番号 1 から始まる配列 tree で表現する場合、要素番号 i（$i ＞ 1$）のノードの親ノードが格納されている要素番号を求める式はどれか。



【解答群】

ア　i × 2

イ　i × 2 ＋ 1

ウ　i ÷ 2 の商

エ　i － 1



---



### 問5：葉ノードの判定とカウント

次の関数 countLeaves は、二分木に含まれる「葉（子を持たないノード）」の総数を数えて返す。空欄に入る正しい条件式を選べ。


〔プログラム〕

〇整数型: countLeaves(Node: node)

    if (node が 未定義 である)

        return 0

    endif

    if (【　空欄　】)

        return 1

    endif

    return countLeaves(node.left) ＋ countLeaves(node.right)



【解答群】

ア　node.left が 未定義 である

イ　node.right が 未定義 である

ウ　node.left が 未定義 かつ node.right が 未定義 である

エ　node.left が 未定義 または node.right が 未定義 である



---



### 解答と解説



1.  正解：イ

     解説：「通りがけ順」は「左→自→右」の順で処理するため、自分を出力した後は右の子を再帰的に呼び出す inOrder(node.right) が入ります。

2.  正解：ア

     解説：二分探索木のルールでは「左の子 ＜ 親 ＜ 右の子」となるため、探している値が現在のノードより小さければ左の枝に進みます。

3.  正解：イ

     解説：木全体の高さは、「左右の子の高さのうち高い方」に「自分自身の分（+1）」を加えたものになります。

4.  正解：ウ

     解説：要素番号 1 から始まる配列表現では、親は i/2、左の子は 2i、右の子は 2i+1 で求められます。

5.  正解：ウ

     解説：葉ノードとは「左の子も右の子も存在しない」ノードのことなので、両方が「未定義」であることを and で判定します。