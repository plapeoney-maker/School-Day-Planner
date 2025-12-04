<Html .....> 
# School-Day-Planner
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';

const rootElement = document.getElementById('root');
if (!rootElement) {
  throw new Error("Could not find root element to mount to");
}

const root = ReactDOM.createRoot(rootElement);
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
import { Activity, Announcement, ClassSchedule, DressCode, Duty, User, UserRole } from "./types";

export const CURRENT_USER: User = {
  id: 'u1',
  name: 'ครูน่ารัก สมใจ',
  role: UserRole.TEACHER,
  position: 'ครูชำนาญการ',
  department: 'สังคมศึกษา ศาสนา และวัฒนธรรม',
  avatarUrl: 'https://picsum.photos/200/200'
};

export const DRESS_CODES: DressCode[] = [
  { dayOfWeek: 1, title: 'ชุดข้าราชการ', color: 'text-yellow-700 bg-yellow-100', description: 'สีกากี (เต็มยศ)', icon: 'Briefcase' },
  { dayOfWeek: 2, title: 'ชุดกีฬา', color: 'text-pink-700 bg-pink-100', description: 'เสื้อโปโลสีชมพู กางเกงวอร์ม', icon: 'Activity' },
  { dayOfWeek: 3, title: 'ชุดลูกเสือ', color: 'text-green-700 bg-green-100', description: 'เครื่องแบบลูกเสือครู', icon: 'Award' },
  { dayOfWeek: 4, title: 'ชุดผ้าไทย', color: 'text-orange-700 bg-orange-100', description: 'ลายประจำจังหวัด', icon: 'Shirt' },
  { dayOfWeek: 5, title: 'ชุดสุภาพ', color: 'text-blue-700 bg-blue-100', description: 'เสื้อเชิ้ตโรงเรียน', icon: 'User' },
];

export const MOCK_ACTIVITIES: Activity[] = [
  {
    id: 'a1',
    title: 'เข้าแถวหน้าเสาธง',
    description: 'กิจกรรมหน้าเสาธงประจำสัปดาห์',
    startTime: '07:45',
    endTime: '08:30',
    location: 'ลานอเนกประสงค์',
    type: 'CEREMONY',
    inCharge: 'ฝ่ายกิจการนักเรียน',
    date: '2024-05-20' // Monday
  },
  {
    id: 'a2',
    title: 'ประชุมหมวดสังคมศึกษาฯ',
    description: 'วางแผนการสอนภาคเรียนที่ 1',
    startTime: '15:30',
    endTime: '16:30',
    location: 'ห้องประชุมสังคมฯ',
    type: 'MEETING',
    inCharge: 'หัวหน้าหมวดสังคม',
    date: '2024-05-20'
  },
  {
    id: 'a3',
    title: 'กิจกรรมกีฬาสีซ้อมย่อย',
    description: 'นักเรียนซ้อมเชียร์',
    startTime: '14:30',
    endTime: '16:00',
    location: 'สนามฟุตบอล',
    type: 'SPORTS',
    inCharge: 'ครูพละ',
    date: '2024-05-21' // Tuesday
  }
];

export const MOCK_DUTIES: Duty[] = [
  {
    id: 'd1',
    title: 'เวรประจำวันหน้าประตู',
    date: '2024-05-20',
    timeSlot: '07:00 - 08:00',
    location: 'ประตู 1',
    isCompleted: true,
    type: 'GATE'
  },
  {
    id: 'd2',
    title: 'ดูแลความเรียบร้อยโรงอาหาร',
    date: '2024-05-20',
    timeSlot: '11:30 - 12:30',
    location: 'โรงอาหาร',
    isCompleted: false,
    type: 'LUNCH'
  },
  {
    id: 'd4',
    title: 'เวรธนาคารโรงเรียน',
    date: '2024-05-20',
    timeSlot: '07:30 - 08:00',
    location: 'ห้องธนาคารโรงเรียน',
    isCompleted: false,
    type: 'DEPARTMENT'
  },
  {
    id: 'd5',
    title: 'กรอกคะแนนเก็บ (SGS)',
    date: '2024-05-20',
    timeSlot: 'Free Time',
    location: 'ห้องวิชาการ',
    isCompleted: false,
    type: 'DEPARTMENT'
  },
  {
    id: 'd6',
    title: 'ส่งแผนการสอน (วิชาการ)',
    date: '2024-05-21',
    timeSlot: 'ก่อน 16:30',
    location: 'ห้องธุรการ',
    isCompleted: false,
    type: 'DEPARTMENT'
  },
  {
    id: 'd3',
    title: 'ตรวจการบ้าน ม.3/1',
    date: '2024-05-22',
    timeSlot: 'Free Time',
    location: 'ห้องพักครู',
    isCompleted: false,
    type: 'OTHER'
  }
];

export const MOCK_CLASSES: ClassSchedule[] = [
  {
    id: 'c1',
    subjectName: 'สังคมศึกษาพื้นฐาน',
    subjectCode: 'ส23101',
    room: 'ห้อง 302',
    timeSlot: '08:30 - 09:20',
    className: 'ม.3/1',
    date: '2024-05-20'
  },
  {
    id: 'c2',
    subjectName: 'ประวัติศาสตร์ไทย',
    subjectCode: 'ส23102',
    room: 'ห้อง 303',
    timeSlot: '09:20 - 10:10',
    className: 'ม.3/2',
    date: '2024-05-20'
  },
  {
    id: 'c3',
    subjectName: 'พระพุทธศาสนา',
    subjectCode: 'ส30101',
    room: 'ห้องจริยธรรม',
    timeSlot: '13:30 - 15:10',
    className: 'ม.5/4',
    date: '2024-05-20'
  }
];

export const MOCK_ANNOUNCEMENTS: Announcement[] = [
  {
    id: 'an1',
    title: 'แจ้งกำหนดการส่งแผนการสอน',
    content: 'ขอให้คุณครูทุกท่านส่งแผนการสอนภายในวันศุกร์ที่ 24 พฤษภาคม นี้',
    author: 'ฝ่ายวิชาการ',
    date: '2024-05-19',
    priority: 'HIGH'
  },
  {
    id: 'an2',
    title: 'ซ่อมบำรุงระบบอินเทอร์เน็ต',
    content: 'จะมีการปิดปรับปรุงระบบในวันเสาร์ที่ 25 พฤษภาคม เวลา 09.00 - 12.00 น.',
    author: 'งานโสตฯ',
    date: '2024-05-18',
    priority: 'NORMAL'
  }
];
import React, { useState } from 'react';
import Layout from './components/Layout';
import Dashboard from './views/Dashboard';
import CalendarView from './views/CalendarView';
import DutiesView from './views/DutiesView';
import AnnouncementsView from './views/AnnouncementsView';
import ProfileView from './views/ProfileView';
import AIChatView from './views/AIChatView';

const App: React.FC = () => {
  const [activeTab, setActiveTab] = useState('dashboard');
  const [showChat, setShowChat] = useState(false);

  // Intercept chat tab selection
  const handleTabChange = (tab: string) => {
    if (tab === 'ai-chat') {
      setShowChat(true);
    } else {
      setActiveTab(tab);
    }
  };

  const renderView = () => {
    switch (activeTab) {
      case 'dashboard': return <Dashboard />;
      case 'calendar': return <CalendarView />;
      case 'duties': return <DutiesView />;
      case 'notices': return <AnnouncementsView />;
      case 'profile': return <ProfileView />;
      default: return <Dashboard />;
    }
  };

  return (
    <>
      <Layout activeTab={activeTab} setActiveTab={handleTabChange}>
        {renderView()}
      </Layout>
      {showChat && <AIChatView onClose={() => setShowChat(false)} />}
    </>
  );
};

export default App;
