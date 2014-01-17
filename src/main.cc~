/* -*- Mode: C++; indent-tabs-mode: t; c-basic-offset: 4; tab-width: 4 -*- */
/*
 * main.cc
 * Copyright (C) 2012 Szymon Sieciński <szymon.siecinski@gmail.com>
 * 
 * Xsampa2IPA is free software: you can redistribute it and/or modify it
 * under the terms of the GNU General Public License as published by the
 * Free Software Foundation, either version 3 of the License, or
 * (at your option) any later version.
 * 
 * Xsampa2IPA is distributed in the hope that it will be useful, but
 * WITHOUT ANY WARRANTY; without even the implied warranty of
 * MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
 * See the GNU General Public License for more details.
 * 
 * You should have received a copy of the GNU General Public License along
 * with this program.  If not, see <http://www.gnu.org/licenses/>.
 */

#include <gtkmm.h>
#include <iostream>
//biblioteka Boost do zastępowania textów
#include<boost/algorithm/string/replace.hpp>

#include "config.h"

#ifdef ENABLE_NLS
#  include <libintl.h>
#endif
Gtk::TextView* xsampa;
Gtk::TextView* ipa;
Glib::RefPtr<Gtk::TextBuffer> text1;
Glib::RefPtr<Gtk::TextBuffer> text2;
Gtk::MenuItem* closeapp;
Gtk::MenuItem* about;
Gtk::MenuItem* clear;
Glib::RefPtr<Gtk::Clipboard> safe;

/* For testing propose use the local (not installed) ui file */
 #define UI_FILE PACKAGE_DATA_DIR"/ui/xsampa2ipa.ui" 
/*#define UI_FILE "src/xsampa2ipa.ui"*/

void CloseApp()
{
	Gtk::Main::quit();
}

void ClearText()
{
	if(xsampa && ipa)
	{
		text1->set_text("");
		text2->set_text("");
	}
}

void Convert()
{
	if(xsampa && ipa)
	{
		std::string Content = text1->get_text().raw();
		boost::replace_all(Content, "b_<", "ɓ");
		boost::replace_all(Content, "d`", "ɖ");
		boost::replace_all(Content, "b_<", "ɓ");
		boost::replace_all(Content, "d`", "ɖ");
		boost::replace_all(Content, "d_\\<", "ɗ");
		boost::replace_all(Content, "g_<", "ɠ");
		boost::replace_all(Content, "h\\", "ɦ");
		boost::replace_all(Content, "i\\", "ɨ");
		boost::replace_all(Content, "j\\", "ʝ");
		boost::replace_all(Content, "l`", "ɭ");
		boost::replace_all(Content, "l\\", "ɺ");
		boost::replace_all(Content, "n`", "ɳ");
		boost::replace_all(Content, "p\\", "ɸ");
		boost::replace_all(Content, "r`", "ɽ");
		boost::replace_all(Content, "r\\`", "ɻ");
		boost::replace_all(Content, "r\\", "ɹ");
		boost::replace_all(Content, "s`", "ʂ");
		boost::replace_all(Content, "s\\", "ɕ");
		boost::replace_all(Content, "t`", "ʈ");
		boost::replace_all(Content, "u\\", "ʉ");
		boost::replace_all(Content, "v\\", "ʋ");
		boost::replace_all(Content, "x\\", "ɧ");
		boost::replace_all(Content, "z`", "ʐ");
		boost::replace_all(Content, "z\\", "ʑ");
		boost::replace_all(Content, "A", "ɑ");
		boost::replace_all(Content, "B\\", "ʙ");
		boost::replace_all(Content, "B", "β");
		boost::replace_all(Content, "C", "ç");
		boost::replace_all(Content, "D", "ð");
		boost::replace_all(Content, "E", "ɛ");
		boost::replace_all(Content, "F", "ɱ");
		boost::replace_all(Content, "G\\_<", "ʛ");
		boost::replace_all(Content, "_G", "ˠ");
		boost::replace_all(Content, "G\\", "ɢ");
		boost::replace_all(Content, "G", "ɣ");
		boost::replace_all(Content, "H\\", "ʜ");
		boost::replace_all(Content, "H", "ɥ");
		boost::replace_all(Content, "I\\", "ᵻ");
		boost::replace_all(Content, "I", "ɪ");
		boost::replace_all(Content, "J\\_<", "ʄ");
		boost::replace_all(Content, "J\\", "ɟ");
		boost::replace_all(Content, "J", "ɲ");
		boost::replace_all(Content, "K\\", "ɮ");
		boost::replace_all(Content, "K", "ɬ");
		boost::replace_all(Content, "L\\", "ʟ");
		boost::replace_all(Content, "L", "ʎ");
		boost::replace_all(Content, "M\\", "ɰ");
		boost::replace_all(Content, "M", "ɯ");
		boost::replace_all(Content, "N\\", "ɴ");
		boost::replace_all(Content, "N", "ŋ");
		boost::replace_all(Content, "O\\", "ʘ");
		boost::replace_all(Content, "O", "ɔ");
		boost::replace_all(Content, "P", "ʋ");
		boost::replace_all(Content, "Q", "ɒ");
		boost::replace_all(Content, "R\\", "ʀ");
		boost::replace_all(Content, "R", "ʁ");
		boost::replace_all(Content, "S", "ʃ");
		boost::replace_all(Content, "T", "θ");
		boost::replace_all(Content, "U\\", "ᵿ");
		boost::replace_all(Content, "U", "ʊ");
		boost::replace_all(Content, "V", "ʌ");
		boost::replace_all(Content, "W", "ʍ");
		boost::replace_all(Content, "_X", "̆");
		boost::replace_all(Content, "X\\", "ħ");
		boost::replace_all(Content, "X", "χ");
		boost::replace_all(Content, "Y", "ʏ");
		boost::replace_all(Content, "Z", "ʒ");
		boost::replace_all(Content, "=\\", "ǂ");
		boost::replace_all(Content, "-\"", "‿");
		boost::replace_all(Content, "%", "ˌ");
		boost::replace_all(Content, "\'", "ʲ");
		boost::replace_all(Content, "_j", "ʲ");
		boost::replace_all(Content, ":\\", "ˑ");
		boost::replace_all(Content, ":", "ː");
		boost::replace_all(Content, "ts", "ʦ");
		boost::replace_all(Content, "t-s", "ts");
		boost::replace_all(Content, "tS", "ʧ");
		boost::replace_all(Content, "t-S", "tʃ");
		boost::replace_all(Content, "d-z", "dz");
		boost::replace_all(Content, "dz", "ʣ");
		boost::replace_all(Content, "d-Z", "dʒ");
		boost::replace_all(Content, "dZ", "ʤ");
		boost::replace_all(Content, "t-s\\", "tɕ");
		boost::replace_all(Content, "ts\\", "ʨ");
		boost::replace_all(Content, "d-z\\", "dʑ");
		boost::replace_all(Content, "dz\\", "ʥ");
		boost::replace_all(Content, "t-K", "tɬ");
		boost::replace_all(Content, "tK", "t͡ɬ");
		boost::replace_all(Content, "N-m", "ŋm");
		boost::replace_all(Content, "Nm", "ŋ͡m");
		boost::replace_all(Content, "t-K", "ʧ");
		boost::replace_all(Content, "tK", "");
		boost::replace_all(Content, "k-p\\", "kp");
		boost::replace_all(Content, "kp", "k͡p");
		boost::replace_all(Content, "g-b", "gb");
		boost::replace_all(Content, "gb", "ɡ͡b");
		boost::replace_all(Content, "@\\", "ɘ");
		boost::replace_all(Content, "@", "ə");
		boost::replace_all(Content, "{", "æ");
		boost::replace_all(Content, "}", "ʉ");
		boost::replace_all(Content, "1", "ɨ");
		boost::replace_all(Content, "2", "ø");
		boost::replace_all(Content, "3", "ɜ");
		boost::replace_all(Content, "3\\", "ɞ");
		boost::replace_all(Content, "4", "ɾ");
		boost::replace_all(Content, "5", "ɫ");
		boost::replace_all(Content, "6", "ɐ");
		boost::replace_all(Content, "7", "ɤ");
		boost::replace_all(Content, "8", "ɵ");
		boost::replace_all(Content, "9", "œ");
		boost::replace_all(Content, "&", "ɶ");
		boost::replace_all(Content, "?\\", "ʕ");
		boost::replace_all(Content, "?", "ʔ");
		boost::replace_all(Content, "{", "æ");
		boost::replace_all(Content, "}", "ʉ");
		boost::replace_all(Content, "1", "ɨ");
		boost::replace_all(Content, "2", "ø");
		boost::replace_all(Content, "3\\", "ɞ");
		boost::replace_all(Content, "3", "ɜ");
		boost::replace_all(Content, "4", "ɾ");
		boost::replace_all(Content, "5", "ɫ");
		boost::replace_all(Content, "6", "ɐ");
		boost::replace_all(Content, "7", "ɤ");
		boost::replace_all(Content, "8", "ɵ");
		boost::replace_all(Content, "9", "œ");
		boost::replace_all(Content, "&", "ɶ");
		boost::replace_all(Content, "?", "ʔ");
		boost::replace_all(Content, "~", "̃");
		boost::replace_all(Content, "_~", "̃");
		boost::replace_all(Content, "=", "̩");
		boost::replace_all(Content, "_=", "̩");
		boost::replace_all(Content, "_h", "ʰ");
		boost::replace_all(Content, "_w", "ʷ");
		boost::replace_all(Content, "<\\", "ʢ");
		boost::replace_all(Content, "\\>", "ʡ");
		boost::replace_all(Content, "_^", "̯");
		boost::replace_all(Content, "_0", "̥");
		boost::replace_all(Content, "_d", "̪");
		boost::replace_all(Content, "_v", "̬");
		boost::replace_all(Content, "_a", "̺");
		boost::replace_all(Content, "_\"", "̈");
		boost::replace_all(Content, "!\\", "ǃ");
		boost::replace_all(Content, "!", "ꜜ");
		boost::replace_all(Content, "|\\|\\", "ǁ");
		boost::replace_all(Content, "|\\", "ǀ");
		boost::replace_all(Content, "||", "‖");
		Glib::ustring buffer(Content);
		text2->set_text(buffer);
	}
}

void aboutprogram()
{
	Gtk::AboutDialog about;
	std::vector<Glib::ustring> autorzy;
	about.set_name("X-SAMPA2API");
	autorzy.push_back("Szymon Sieciński <szymon.siecinski@gmail.com>");
	about.set_authors(autorzy);
	about.set_version("Wersja 0.1");
	about.set_comments("Program zamieniający zapis w X-SAMPA na zapis w API");
	about.set_license("X-SAMPA2API is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.\nX-SAMPA2API is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.\nYou should have received a copy of the GNU General Public License along with this program.  If not, see <http://www.gnu.org/licenses/>.");
	about.set_wrap_license(true);
	about.run();
}

int
main (int argc, char *argv[])
{
	Gtk::Main kit(argc, argv);


	//Load the Glade file and instiate its widgets:
	Glib::RefPtr<Gtk::Builder> builder;
	try
	{
		builder = Gtk::Builder::create_from_file(UI_FILE);
	}
	catch (const Glib::FileError & ex)
	{
		std::cerr << ex.what() << std::endl;
		return 1;
	}
	Gtk::Window* main_win = 0;
	builder->get_widget("main_window", main_win);
	builder->get_widget("textview1", xsampa);
	builder->get_widget("textview2", ipa);
	builder->get_widget("about", about);
	builder->get_widget("zamek", closeapp);
	builder->get_widget("czysc", clear);

	if(xsampa)
	{
		text1 = xsampa->get_buffer();
		text1->signal_changed().connect(sigc::ptr_fun(&Convert));
	}

	if(ipa)
	{
		text2 = ipa->get_buffer();
	}

	if(about)
	{
		about->signal_activate().connect(sigc::ptr_fun(&aboutprogram));
	}

	if(closeapp)
	{
		closeapp->signal_activate().connect(sigc::ptr_fun(&CloseApp));
	}

	if(clear)
	{
		clear->signal_activate().connect(sigc::ptr_fun(&ClearText));
	}

	if (main_win)
	{
		kit.run(*main_win);
	}
	return 0;
}
