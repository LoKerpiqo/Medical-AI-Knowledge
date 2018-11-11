# Medical-AI-Knowledge
Everything learned for medical AI, especially medical imaging such as CT, MRI, PET, and PET/CT, PET/MRI during my PhD study.

## CT Basic Knowledge: 窗位与窗中心

CT能识别人体内2000个不同灰阶的密度差别，而人的眼睛识别16个灰阶度。所以，人眼在CT图像上能分别的CT值应该为125Hu（2000/16）。即，人体内不同组织CT值只有相差125Hu以上，才能为人眼识别。其中，人体软组织CT值多变化在20-50Hu之间，人眼无法识别。为此，必须进行分段观察，才能使CT的优点反映出来。
观察的CT值范围，称为**窗宽**,观察的中心CT值，称为**窗位or窗中心**。

**窗宽**指CT图像所显示的CT值范围。在此范围内的组织结构按密度高低从白到黑分为16个灰阶以供观察。
例如，窗宽选定为100 Hu ，则人眼可分辨的CT值为100 / 16 =6 . 25 Hu ，即2 种组织CT值相差在6 . 25Hu以上者即可为人眼所识别。
因此，窗宽的宽窄直接影响图像的清晰度与对比度。
如果使用窄的窗宽，则显示的CT 值范围小，每一灰阶代表的CT 值幅度小，对比度强，适于观察密度接近的组织结构（如脑组织）。
反之，如果使用宽的窗宽，则显示的CT值范围大，每一灰阶代表的CT 值幅度大，则图像对比度差，但密度均匀，适于观察密度差别大的结构（如骨与软组织）。

**窗位**（窗中心）指窗宽范围内均值或中心值。
比如一幅CT图像，窗宽为100Hu，窗位选在0Hu；
则以窗位为中心（0Hu），向上包括+50Hu，向下包括-50Hu，凡是在这个100Hu 范围内的组织均可显示出来并为人眼所识别。
凡是大于+50Hu 的组织均为白色；凡是小子-50Hu 的组织均为黑色，其密度差异无法显示。
人眼只能识别土50Hu 范围内的CT 值，每一个灰阶的CT 值范围是100 / 16＝6 . 25 Hu 。
原则上说，
>窗位应该等于或接近需要观察的CT 值；
>窗宽应能反映该组织或病变的CT 值变化范围

## PET Working Principle & PET/CT Application
PET/CT一般建议用于常规检查不能确诊的可疑恶性肿瘤患者、肿瘤的分期评估、肿瘤治疗后的病情监测和复发的判定、冠心病和心肌病的病情评价、精神疾病的脑内病灶定位等
当被高度怀疑患癌，当面临恶性肿瘤威胁，对于这些有适应症患者接受PET/CT检查的受益明显大于较低概率的辐射风险，甚至使受检者获得挽救生命的机会。

PET/CT 常用于**肺癌，鼻咽癌，食管癌，肝癌，肠道肿瘤，淋巴瘤，生殖系统瘤，骨骼系统瘤**的诊断

**原理**:被誉为世纪分子的18F-FDG（氟代脱氧葡萄糖）是目前临床运用的主力显像剂，
通过准确反映内器官/组织的葡萄糖代谢水平能够满足很多肿瘤的诊断需求（代谢高不一定恶性噢！）
以代谢显像和定量分析为基础的PET/CT，利用人体代谢所必需的物质，
如：葡萄糖、脂肪酸、核酸和蛋白质等标记短寿命的放射性核素制成显像剂注入人体后进行扫描成像。 
在恶性肿瘤组织呈现出的高代谢图像会和正常低代谢的情况有着强烈的对比，反应映出来后就可对病变进行诊断和分析。

部分肿瘤对FDG没反应，则有别的显像剂，如前列腺癌特异性显像剂11C-Choline，
脑肿瘤11C-Methionine, 反映细胞增殖的18F-flurothymidine（FLT）

>PET-CT除了能够知道肿瘤是不是存在，哪些地方存在，以及肿瘤多大，还能够知道肿瘤是不是活的，活性多大。

#### PET/CT 盲区
PET-CT的相对盲区，**脑和肝**，因为代谢本身较高，且不均匀，PET对其肿瘤的鉴别意义有限。
做了PETCT还要不要做其他检查？要，当然要，首先脑、肝还得靠MRI，
另外，PETCT上的CT是定位用的，是辅助诊断用的，其剂量比常规CT低很多，所以图像质量也达不到常规CT的水平，何况常规CT还可做增强扫描。

此外，PET-CT对淋巴瘤发生的部位也是有“讲究”的，因为靠着显像剂将肿瘤“点亮”而识别肿瘤:
>**淋巴结、脾、肺和骨骼**等“黑暗”区域的淋巴瘤能够被明确识别
>但对于**心脏、中枢神经系统、胃部、肾脏、膀胱**等“明亮”区域，辨别起来就有些困难
