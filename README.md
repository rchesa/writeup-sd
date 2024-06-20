# writeup-sd

1. Class & Object
   - Class : template, mendefinisikan variable yang dimiliki object. `Contoh` : Goods, incoming_goods, outgoing_goods
2. Attribute / Property & Method / Behavior
   - Attribute : variable dalam class
     ```
     protected:
      string goods_id;
      string goods_name;
      string goods_category;
      int stock_amount;
      string date;
     ```
   - Method : fungsi dalam class
     ```
     public:
      Goods(string goods_id, string goods_name, string goods_category, int stock_amount, string date)
        : goods_id(goods_id), goods_name(goods_name), goods_category(goods_category), stock_amount(stock_amount), date(date) {}

        string get_goods_code() const 
      { 
        return goods_id; 
      }
      string get_goods_name() const 
      { 
       return goods_name; 
      }
      string get_goods_category() const 
      { 
       return goods_category; 
      }
    
      int get_stock_amount() const 
      {
        return stock_amount; 
      }
      string get_date() const 
      {   
        return date; 
      }

      void set_goods_name(const string &goods_name) 
      { 
        this ->goods_name = goods_name; 
      }
    
      void set_goods_category(const string &goods_category) 
      { 
        this ->goods_category = goods_category; 
      }
    
      void set_stock_amount(int stock_amount) 
      { 
        this ->stock_amount = stock_amount; 
      }
    
      void set_data(const string &date) 
      { 
        this->date = date; 
      }

      virtual void display_goods() const 
      {
        cout << "ID: " << goods_id << "\nNama: " << goods_name << "\nKategori: " << goods_category
             << "\nJumlah: " << stock_amount << "\nTanggal: " << date << endl;
      }
     ```
3. Constructor : fungsi yang dipanggil saat object dari class dibuat
     ```
     public:
         Goods(string goods_id, string goods_name, string goods_category, int stock_amount, string date)
          : goods_id(goods_id), goods_name(goods_name), goods_category(goods_category), stock_amount(stock_amount), date(date) {}
     ```
4. Setter & Getter : `setter` mengubah, `getter` mengambil
5. Ecapsulation (Private, Protected dan Public)
   - Private : class hanya dapat diakses dari dalam class itu sendiri
   - Protected : bisa diakses dari dalam class itu sendiri dan dari subclass
   - Public : bisa diakses darimana saja
6. Inheritance : class mengambil properti dari metode class lain.
   ```
   class incoming_goods : public Goods 
    {
    //...
    };

   class outgoing_goods : public Goods 
    {
    //...
    };
   ```
   -> incoming_goods & ougoing_goods merupakan turunan dari Goods
7. Overriding : definisi kembali dari superclass ke subclass
   ```
    class incoming_goods : public Goods 
    {
    public:
        void display_goods() const override 
        {
            Goods::display_goods();
            cout << "Supplier: " << supplier << endl << endl;
        }
    };
   ```
   -> display_goods() di incoming_goods mengoverride display_goods() di Goods.
8. Abstraction : display_goods()   
9. Polymorphism : satu tampilan untuk banyak interaksi. tergantung objek yang digunakan. override     
