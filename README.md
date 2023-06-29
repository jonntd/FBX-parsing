# FBX-parsing


读取fbx mesh 和 materials 
{"meshs": ["pSphere1"],"materials": ["lambert5","lambert3","lambert2","lambert7","lambert1","lambert6","lambert4"]}


import subprocess
import json

fbxconv = r"C:\FBX-parsing.exe"
fbx_file_path = r"C:\test.fbx"
shell_cmd = [fbxconv,fbx_file_path]
p = subprocess.Popen(shell_cmd, shell=True, stdout=subprocess.PIPE,stderr=subprocess.STDOUT)
out, err = p.communicate()
fbx_data = json.loads(out)
materials_order = fbx_data['materials']
print(materials_order)
# ['lambert5', 'lambert3', 'lambert2', 'lambert7', 'lambert1', 'lambert6', 'lambert4']

