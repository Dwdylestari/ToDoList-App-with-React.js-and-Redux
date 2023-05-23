# Technical Assignment ToDoList App with React.js and Redux

Nama : Dewi Lestari
Tim : FE #4
Challenge : Skilvul - Product Tema Lingkungan
Email : dewilestari300401@gmail.com
Github : Dwdylestari

Komponen React yang disebut TodoList. Komponen ini digunakan untuk menampilkan daftar tugas (todo list) beserta fitur-fitur pengelolaannya, seperti menambahkan tugas baru, mengupdate tugas, menghapus tugas, dan mengurutkan tugas berdasarkan kriteria tertentu.

Berikut adalah penjelasan lebih detail mengenai kode tersebut:

1. Import:

- useEffect dan useState dari "react": Hooks yang digunakan untuk mengatur efek samping dan state dalam komponen.
- useDispatch dan useSelector dari "react-redux": Hooks yang digunakan untuk berinteraksi dengan store Redux.
- setTodoList, addTodo, updateTodo, sortTodo, dan toggleCompleted dari "../ToDoSlice": Fungsi-fungsi aksi (action creators) yang digunakan untuk memanipulasi state to-do dalam store Redux.
- TiPencil dari "react-icons/ti" dan BsTrash dari "react-icons/bs": Ikon yang digunakan untuk tombol pengeditan dan penghapusan to-do.
- empty dari "../assets/add.png": Gambar yang ditampilkan pada halaman jika tidak ada to-do.

2. Fungsi TodoList():

- Mendeklarasikan state menggunakan hooks:

  > showModal: State untuk mengontrol tampilan modal (dialog) untuk menambahkan atau mengedit to-do.
  > currentTodo: State untuk menyimpan to-do yang sedang diedit.
  > newTask: State untuk menyimpan nilai input baru dari form.
  > Mendapatkan akses ke dispatch dan state dari Redux menggunakan hooks useDispatch dan useSelector.

- useEffect:

  > Digunakan untuk menyimpan dan mengambil daftar to-do dari localStorage saat komponen dimount dan saat todoList berubah.
  > Jika todoList memiliki elemen, maka daftar to-do disimpan dalam localStorage dengan menggunakan localStorage.setItem().
  > Saat komponen dimount, daftar to-do diambil dari localStorage menggunakan localStorage.getItem() dan diupdate ke dalam state menggunakan dispatch(setTodoList(localTodoList)).

- Fungsi handleAddTodo(task):

  > Digunakan untuk menambahkan to-do baru.
  > Memeriksa apakah nilai task yang diinputkan tidak kosong.
  > Jika kosong, muncul alert.
  > Jika tidak kosong, melakukan dispatch addTodo dengan task dan id yang dihasilkan menggunakan Date.now().
  > Mengosongkan nilai newTask.
  > Menampilkan modal dengan setShowModal(true).

- Fungsi handleUpdateToDoList(id, task):

  > Digunakan untuk mengupdate to-do yang ada.
  > Memeriksa apakah nilai task yang diinputkan tidak kosong.
  > Jika kosong, muncul alert.
  > Jika tidak kosong, melakukan dispatch updateTodo dengan task dan id yang diberikan.
  > Menyembunyikan modal dengan setShowModal(false).

- Fungsi handleDeleteToDo(id):

  > Digunakan untuk menghapus to-do berdasarkan id.
  > Membuat salinan daftar to-do yang telah diperbarui menggunakan filter().
  > Memperbarui state to-do dengan dispatch setTodoList(updatedToDoList).
  > Memperbarui localStorage dengan daftar to-do yang diperbarui menggunakan localStorage.setItem().

- Fungsi handleSort(sortCriteria):

  > Digunakan untuk mengatur kriteria pengurutan to-do.
  > Melakukan dispatch sortTodo dengan kriteria yang diberikan.

- Membuat variabel sortToDoList:

  > Menyaring daftar to-do berdasarkan kriteria pengurutan yang dipilih.
  > Jika kriteria adalah "All", semua to-do ditampilkan.
  > Jika kriteria adalah "Completed", hanya to-do yang selesai (completed) yang ditampilkan.
  > Jika kriteria adalah "Active", hanya to-do yang aktif (belum selesai) yang ditampilkan.

- Fungsi handleToggleCompleted(id):

  > Digunakan untuk mengubah status selesai (completed) dari to-do berdasarkan id.
  > Melakukan dispatch toggleCompleted dengan id yang diberikan.

- Render JSX:

  > Menampilkan modal jika showModal bernilai true.
  > Menampilkan form input untuk menambah atau mengedit to-do.
  > Tombol "Save" dan "Cancel" untuk mengupdate atau membatalkan edit to-do.
  > Tombol "Add" untuk menambahkan to-do baru.
  > Menampilkan pesan jika daftar to-do kosong.
  > Menampilkan dropdown untuk memilih kriteria pengurutan to-do.
  > Menampilkan daftar to-do yang telah diurutkan dan dapat diklik untuk mengubah status selesai atau melakukan edit atau hapus to-do.

3. Export TodoList sebagai komponen default.

Kode tersebut menggambarkan komponen React yang dapat digunakan untuk membuat sebuah aplikasi sederhana untuk mengelola daftar tugas (todo list) dengan fitur-fitur utama seperti menambahkan, mengedit, dan menghapus tugas, serta mengurutkan dan menandai tugas selesai. Komponen ini menggunakan Redux untuk manajemen state to-do list.

Komponen React yang disebut Heading. Komponen ini digunakan untuk menampilkan judul atau heading yang berisi pertanyaan "What's the plan for today?" dengan tampilan teks berukuran besar dan tebal.

Berikut adalah penjelasan lebih detail mengenai kode tersebut:

1. Import:

- React dari modul "react": Diperlukan untuk membuat komponen React.

2. Fungsi Heading():

- Merupakan komponen fungsional yang tidak menerima prop (properti) apa pun.
- Mengembalikan elemen JSX yang berupa sebuah div dengan class name "text-center text-4xl font-bold".
- Isi teks di dalam div adalah "What's the plan for today?".
- Class name "text-center" digunakan untuk mengatur teks menjadi rata tengah.
- Class name "text-4xl" mengatur ukuran teks menjadi sangat besar.
- Class name "font-bold" mengatur teks menjadi tebal.

3. Export Heading sebagai komponen default.

Kode tersebut adalah komponen sederhana yang dapat digunakan untuk menampilkan judul atau heading dengan gaya tampilan yang telah ditentukan. Komponen ini tidak memiliki ketergantungan pada state atau properti, sehingga dapat digunakan dengan mudah di dalam komponen-komponen lain dalam aplikasi React.
