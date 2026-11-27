        }
      ];
      saveLocal(STORAGE_KEYS.hpp, state.hpp);
      saveLocal(STORAGE_KEYS.bep, state.bep);
      saveLocal(STORAGE_KEYS.stok, state.stok);
      saveLocal(STORAGE_KEYS.pendapatan, state.pendapatan);
      renderAllTablesAndKPIs();
      refreshHppDropdowns();
      renderRevenueChart();
      showToast('Data contoh berhasil dimuat ke 4 modul.', 'success');
    }
    // =========================================================================
    // INISIALISASI APLIKASI
    // =========================================================================
    document.addEventListener('DOMContentLoaded', () => {
      // Set default tanggal & bulan hari ini
      const today = new Date();
      document.getElementById('stok-tanggal').value = today.toISOString().slice(0, 10);
      document.getElementById('rev-bulan').value = today.toISOString().slice(0, 7);
      // Baris bahan baku awal pada Modul 1
      addBahanRow('Biji Kopi Espresso', 'gr', 220, 1000);
      addBahanRow('Susu UHT Full Cream', 'ml', 18, 6000);
      addBahanRow('Gula Aren Cair', 'ml', 35, 1500);
      calculateHPP();
      calculateBEP();
      calculateStok();
      calculatePendapatan();
      renderAllTablesAndKPIs();
      refreshHppDropdowns();
      renderRevenueChart();
      updateConnectionUI();
      lucide.createIcons();
    });
  </script>
</body>
</html>
