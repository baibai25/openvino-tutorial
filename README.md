# openvino-tutorial

## Arch
- Install intel-npu-driver
  - https://snapcraft.io/intel-npu-driver
- Install latest openvino
  - openvino>=2025.1.0
  - 古いバージョンはNPU関連の処理が入っていない
- Install Level-Zero loader
  - `sudo pacman -S level-zero-loader`
- Link with snap
  - `/snap/intel-npu-driver/current/`から`libze_intel_npu.so.1`を探す
  - `/usr/lib/`にリンクを作成
    - `sudo ln -s /snap/intel-npu-driver/current/usr/lib/x86_64-linux-gnu/libze_intel_npu.so.1 /usr/lib/`
- Check

```
python - <<'PY'
from openvino import Core
print(Core().available_devices)
PY
```

- Note
  - 動作確認・最新情報はここ
    - https://github.com/intel/linux-npu-driver/releases
