import 'package:flutter/material.dart';

void main() {
  runApp(SekolahApp());
}

class SekolahApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Menu Aplikasi Sekolah',
      debugShowCheckedModeBanner: false,
      home: MenuScreen(),
    );
  }
}

class MenuScreen extends StatelessWidget {
  final List<MenuItem> menuItems = [
    MenuItem(icon: Icons.book, label: 'Materi', color: Colors.blue),
    MenuItem(icon: Icons.assignment, label: 'Tugas', color: Colors.green),
    MenuItem(icon: Icons.access_time, label: 'Jadwal', color: Colors.orange),
    MenuItem(icon: Icons.star, label: 'Nilai', color: Colors.red),
    MenuItem(icon: Icons.group, label: 'Guru', color: Colors.purple),
    MenuItem(icon: Icons.notifications, label: 'Info', color: Colors.teal),
    MenuItem(icon: Icons.chat, label: 'Chat', color: Colors.indigo),
    MenuItem(icon: Icons.settings, label: 'Pengaturan', color: Colors.grey),
    MenuItem(icon: Icons.exit_to_app, label: 'Keluar', color: Colors.black87),
  ];

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Color(0xFFFDF6FF), // warna background lembut
      appBar: AppBar(
        backgroundColor: Colors.white,
        elevation: 0,
        centerTitle: true,
        title: Text(
          'Menu Aplikasi Sekolah',
          style: TextStyle(color: Colors.black87, fontWeight: FontWeight.bold),
        ),
      ),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: GridView.count(
          crossAxisCount: 3,
          mainAxisSpacing: 20,
          crossAxisSpacing: 20,
          children: menuItems.map((item) {
            return Column(
              mainAxisSize: MainAxisSize.min,
              children: [
                Container(
                  decoration: BoxDecoration(
                    color: item.color.withOpacity(0.1),
                    borderRadius: BorderRadius.circular(16),
                  ),
                  padding: EdgeInsets.all(16),
                  child: Icon(item.icon, color: item.color, size: 36),
                ),
                SizedBox(height: 8),
                Text(
                  item.label,
                  style: TextStyle(fontSize: 14, fontWeight: FontWeight.w500),
                ),
              ],
            );
          }).toList(),
        ),
      ),
    );
  }
}

class MenuItem {
  final IconData icon;
  final String label;
  final Color color;

  MenuItem({required this.icon, required this.label, required this.color});
}

