Reassembly instructions for model_q4f16.onnx

The file was split into 28 part(s) of at least 17 MB each.
All parts are byte slices of the original in ascending index order:

  part001, part002, part003, …

Concatenate them (in order) to get the original file back.

  macOS / Linux:
    cat model_q4f16.onnx.part* > model_q4f16.onnx

  Windows PowerShell:
    $out = [System.IO.File]::Create("model_q4f16.onnx")
    Get-ChildItem -Filter "model_q4f16.onnx.part*" | Sort-Object Name | ForEach-Object {
      $bytes = [System.IO.File]::ReadAllBytes($_.FullName)
      $out.Write($bytes, 0, $bytes.Length)
    }
    $out.Close()

  Windows CMD:
    copy /b model_q4f16.onnx.part001+model_q4f16.onnx.part002+... model_q4f16.onnx

The file model_q4f16.onnx.manifest.json records the exact original size
and byte range of each part, so the concatenation can be verified.
