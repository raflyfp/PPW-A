---
title: 210411100063 Rafly Faldiansyah Putra PPWA

---

 ### Nama : Rafly Faldiansyah Putra
 ### NIM :210411100063
 ### Kelas : PPW A

## **skrip gram**
Skip-gram adalah teknik yang digunakan dalam pemrosesan bahasa alami (NLP), khususnya dalam pembuatan word embeddings. Cara kerjanya adalah dengan mencoba menebak kata-kata di sekitar (konteks) dari sebuah kata yang diberikan. Misalnya, jika kita punya kalimat "kucing suka tidur di sofa", skip-gram akan mengambil satu kata, seperti "kucing", lalu mencoba menebak kata-kata yang muncul di dekatnya, seperti "suka", "tidur", atau "sofa".

Secara singkat, skip-gram melatih model untuk memahami hubungan antar kata dengan memprediksi kata-kata tetangga dari satu kata yang dipilih, sehingga komputer bisa belajar hubungan kata berdasarkan konteks penggunaannya.

### Contoh Penggunaan:

"The man who passes the should swing the sword"
berikut adalah hasil dari skipgram:


| Kata Target | Kata Konteks         |
|-------------|----------------------|
| The         | man                  |
| man         | The, who             |
| who         | man, passes          |
| passes      | who, the             |
| the         | passes, should       |
| should      | the, swing           |
| swing       | should, the          |
| the         | swing, sword         |
| sword       | the                  |

iterasi pertama:

| Kata                | the | man | who | passes | the | should | swing | the | sword |
|---------------------|---|---|---|---|---|---|---|---|---|
| the                 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| man                 | 1 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 |
| who                 | 0 | 1 | 0 | 1 | 0 | 0 | 0 | 0 | 0 |
| passes              | 0 | 0 | 1 | 0 | 1 | 0 | 0 | 0 | 0 |
| the                 | 0 | 0 | 0 | 1 | 0 | 1 | 0 | 0 | 0 |
| should              | 0 | 0 | 0 | 0 | 1 | 0 | 1 | 0 | 0 |
| swing               | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 1 | 0 |
| the                 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 1 |
| sword               | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 |

iterasi kedua :

| Kata     | the | man | who | passes | the | should | swing | the | sword |
|----------|-----|-----|-----|--------|-----|--------|-------|-----|-------|
| the      | 0   | 2   | 1   | 0      | 0   | 0      | 0     | 0   | 0     |
| man      | 2   | 0   | 2   | 1      | 0   | 0      | 0     | 0   | 0     |
| who      | 1   | 2   | 0   | 2      | 1   | 0      | 0     | 0   | 0     |
| passes   | 0   | 1   | 2   | 0      | 2   | 1      | 0     | 0   | 0     |
| the      | 0   | 0   | 1   | 2      | 0   | 2      | 1     | 0   | 0     |
| should   | 0   | 0   | 0   | 1      | 2   | 0      | 2     | 1   | 0     |
| swing    | 0   | 0   | 0   | 0      | 1   | 2      | 0     | 2   | 1     |
| the      | 0   | 0   | 0   | 0      | 0   | 1      | 2     | 0   | 2     |
| sword    | 0   | 0   | 0   | 0      | 0   | 0      | 1     | 2   | 0     |

**Penjelasan:**
Iterasi Pertama: Tabel ini menunjukkan frekuensi kemunculan kata-kata dalam konteks masing-masing. Nilai di dalam tabel merepresentasikan seberapa sering kata target berko-occurrence dengan kata konteks.

Iterasi Kedua: Tabel ini menunjukkan total kemunculan yang lebih besar antara kata-kata, menunjukkan penguatan hubungan antar kata. Nilai yang lebih tinggi menunjukkan bahwa kata-kata ini muncul bersama lebih sering, menunjukkan interaksi yang lebih kuat dalam konteks kalimat yang sama.


## **word embedding**
Word embedding adalah teknik dalam pemrosesan bahasa alami (NLP) yang mengubah kata-kata menjadi vektor angka sehingga komputer bisa memahaminya. Dalam bahasa sederhana, ini seperti memberi setiap kata "koordinat" dalam ruang multidimensi. Kata-kata yang memiliki makna mirip akan memiliki koordinat yang dekat satu sama lain. Misalnya, kata "raja" dan "ratu" akan lebih dekat dibanding "raja" dan "sepeda." 

## **cbow**
CBOW (Continuous Bag of Words) adalah teknik dalam pemrosesan bahasa alami yang bekerja kebalikan dari **skip-gram**. Jika skip-gram mencoba memprediksi kata-kata di sekitar sebuah kata, **CBOW** mencoba menebak kata yang hilang dari konteks kata-kata sekitarnya.

Misalnya, jika kita punya kalimat "kucing ___ tidur di sofa", CBOW akan melihat kata-kata sekitarnya seperti "kucing", "tidur", dan "sofa", lalu mencoba memprediksi kata yang hilang, dalam hal ini "suka". Jadi, CBOW mempelajari hubungan antar kata dengan cara menebak sebuah kata berdasarkan kata-kata yang muncul di sekitarnya.

Secara singkat, CBOW adalah metode untuk mengajarkan komputer memahami kata dengan melihat konteks sekelilingnya dan memprediksi kata yang tepat untuk mengisi kekosongan.1