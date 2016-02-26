# PopupMenu
Android中自定义popupwindow

使用方法：
package com.lidong.popupmenu;

import android.app.Activity;
import android.os.Bundle;
import android.view.View;
import android.view.View.OnClickListener;
import android.widget.ImageView;
import android.widget.Toast;


public class MainActivity extends Activity {

	private ImageView iv_menu;
	private PopupMenu popupMenu;

	@Override
	protected void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState);
		setContentView(R.layout.activity_main);
		String[] abs = new String[]{"关于我们", "检查更新", "意见反馈"};
		popupMenu = new PopupMenu(this,abs);

		iv_menu = (ImageView) findViewById(R.id.iv_menu);

		iv_menu.setOnClickListener(new OnClickListener() {

			@Override
			public void onClick(View v) {
				popupMenu.showLocation(R.id.iv_menu);// 设置弹出菜单弹出的位置
				// 设置回调监听，获取点击事件
				popupMenu.setOnItemClickListener(new PopupMenu.OnItemClickListener() {

					@Override
					public void onClick(PopupMenu.MENUITEM item, String str) {
						Toast.makeText(getApplication(), str, Toast.LENGTH_SHORT).show();

					}
				});
			}
		});
	}
}
图片展示：

![](https://raw.githubusercontent.com/lidong1665/PopupMenu/master/screenshots/8C2B13845C23D5110AACDAF2F4A6FD50.jpg)
