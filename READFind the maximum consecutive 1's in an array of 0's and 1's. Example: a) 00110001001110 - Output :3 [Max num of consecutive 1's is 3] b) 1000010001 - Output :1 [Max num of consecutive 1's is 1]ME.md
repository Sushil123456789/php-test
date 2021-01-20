static int getMaxOfConsecutiveOnes(String s) {
    int globalMax = 0;
    int currentMax = 0;

    for (int i = 0; i < s.length(); i++) {
      if (s.charAt(i) == '1') {
        currentMax++;
      } else {
        if (currentMax != 0) {
          if (globalMax < currentMax) {
            globalMax = currentMax;
          }
          currentMax = 0;
        }
      }
    }

    // check the end
    if (globalMax < currentMax) {
      globalMax = currentMax;
    }

    return globalMax;
  }


Tests:
{"00110001001110", 3},
  {"1000010001", 1},
  {"00000", 0},
  {"11111", 5}
