#第一个测试文件
#CSS3 动画效果制作彩色流光按钮
<style>
* {
  margin: 0;
  padding: 0;
}
.light-btn {
  text-decoration: none;
  /* 水平垂直居中，后期改掉 */
  position: absolute;
  left: 50%;
  top:50%;
  transform: translate(-50%, -50%);

  font-size: 24px;
  background: linear-gradient(90deg, #03a9f4, #f441a5, #ffeb3b, #03a9f4);
  /* 设置400是因为有4个颜色，第一个数为宽度，高度未设为auto，这样一个颜色的宽度正好是按钮的宽度 */
  background-size: 400%;
  /* 按钮大小和行高 */
  width: 400px;
  height: 100px;
  line-height:100px;

  color: #fff;
  text-align: center;
  text-transform: uppercase;
  border-radius: 50px;
  z-index: 1;
}

.light-btn:hover::before,
.light-btn:hover {
  animation: sun 8s infinite;
}
/* 光晕特效 */
.light-btn::before {
  content: '';
  position: absolute;
  left: -5px;
  right: -5px;
  top: -5px;
  bottom: -5px;
  background: linear-gradient(90deg, #03a9f4, #f441a5, #ffeb3b, #03a9f4);
  background-size: 400%;
  border-radius: 50px;
  filter: blur(10px);
  z-index: -1;
}
@keyframes sun {
	0%{
		background-position: -400% 0;
	}
    100%{
	/* 400是因为有4个颜色，为了无缝循环 */
    	background-position: 0% 0;
  }
}
</style>
