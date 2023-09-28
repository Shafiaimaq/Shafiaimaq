- 👋 Hi, I’m @Shafiaimaq
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Shafiaimaq/Shafiaimaq is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
javascript
import React, { useState } from 'react';
import { View, Text, FlatList } from 'react-native';

const App = () => {
  const [meters, setMeters] = useState([]); // آرایه‌ی میترهای برق

  const addMeter = (serialNumber, currentKilowatt, previousKilowatt) => {
    const newMeter = { serialNumber, currentKilowatt, previousKilowatt };
    setMeters([...meters, newMeter]); // اضافه کردن میتر به آرایه
  };

  return (
    <View>
      <Text>جدول برق</Text>
      <FlatList
        data={meters}
        keyExtractor={(item) => item.serialNumber}
        renderItem={({ item }) => (
          <View>
            <Text>سریال: {item.serialNumber}</Text>
            <Text>کیلووات فعلی: {item.currentKilowatt}</Text>
            <Text>کیلووات گذشته: {item.previousKilowatt}</Text>
          </View>
        )}
      />
    </View>
  );
};

export default App;
